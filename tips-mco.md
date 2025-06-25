# How to Create and Implement Machine Configs

NOTE: THIS IS WORK IN PROGRESS, NOT VALIDATED

OpenShift's **Machine Config Operator (MCO)** is a crucial component for managing the operating system (RHCOS) and cluster-level configurations of your OpenShift nodes. It uses **MachineConfig** objects to define desired configurations and applies them to specific MachineConfigPools.

MachineConfigs leverage Ignition, a configuration format for RHCOS, to apply changes to your nodes. Here's a general process:

1. **Understand MachineConfig and MachineConfigPools:**
    * **MachineConfig (MC):** Defines specific changes to be applied to a node. This can include:
        * Creating, modifying, or deleting files (e.g., in `/etc` or `/var`).
        * Managing `systemd` units (starting, stopping, enabling services).
        * Setting kernel arguments.
        * Managing users and SSH keys.
    * **MachineConfigPool (MCP):** A collection of MachineConfigs applied to a group of nodes with a specific role (e.g., `master`, `worker`). The MCO aggregates all MachineConfigs in an MCP and renders a final Ignition configuration for the nodes in that pool.

2. **Determine the Target Nodes:**
    * Identify which nodes (master, worker, or custom roles) you want to apply the configuration to. This will determine the `machineconfiguration.openshift.io/role` label you use in your MachineConfig.

3. **Craft your MachineConfig (YAML):**
    * MachineConfigs are Kubernetes Custom Resources. You define them in YAML.
    * **Basic Structure:**

        ```yaml
        apiVersion: machineconfiguration.openshift.io/v1
        kind: MachineConfig
        metadata:
          labels:
            machineconfiguration.openshift.io/role: <role> # e.g., worker, master, or a custom role
          name: <your-machineconfig-name> # Often prefixed with a number for ordering (e.g., 99-worker-custom-ntp)
        spec:
          config:
            ignition:
              version: 3.4.0 # Use the appropriate Ignition version for your OCP version
              storage:
                files:
                  - contents:
                      source: data:,<base64-encoded-content> # or inline: | <plain-text-content>
                    mode: 0644
                    path: /path/to/your/file
              systemd:
                units:
                  - name: your-custom-service.service
                    enabled: true
                    contents: |
                      [Unit]
                      Description=My Custom Service
                      After=network-online.target
                      Wants=network-online.target
                      [Service]
                      ExecStart=/usr/local/bin/my-script.sh
                      Restart=always
                      [Install]
                      WantedBy=multi-user.target
          # You can also add kernelArguments, extensions, etc. here
        ```

    * **Using Butane:** For complex Ignition configurations, it's highly recommended to use [Butane](https://docs.openshift.com/container-platform/latest/installing/install_references/install-reference-ignitions.html#butane-overview). Butane allows you to write a more human-readable YAML and then compile it into the Ignition JSON format required by the MachineConfig.
        * Write your configuration in Butane YAML.
        * Compile it to Ignition JSON: `butane --pretty --strict <your-butane-file.yaml> > <your-ignition-config.json>`
        * Embed the Ignition JSON (often base64 encoded) into the `spec.config` field of your MachineConfig.

4. **Apply the MachineConfig:**
    * Once you have your MachineConfig YAML, apply it to your cluster:

        ```bash
        oc create -f <your-machineconfig-file.yaml>
        ```

    * The Machine Config Operator (MCO) will detect the new MachineConfig.
    * The MCO will then update the corresponding MachineConfigPool.
    * Nodes in that pool will enter an "Updating" state, drain their pods, apply the new configuration (which might involve a reboot), and then become "Ready" again.

5. **Monitor the Rollout:**
    * Watch the status of your MachineConfigPools to see the progress:

        ```bash
        oc get mcp
        oc describe mcp <pool-name> # e.g., master or worker
        ```

    * You can also check the status of individual nodes:

        ```bash
        oc get nodes
        oc describe node <node-name>
        ```

    * Look for the `Updated` and `Updating` columns in `oc get mcp` output. Nodes will typically go through a `Ready,SchedulingDisabled` state during the update.

6. **Verify the Changes:**
    * Once the rollout is complete, verify the changes on a node. For example, if you added a file:

        ```bash
        oc debug node/<node-name>
        chroot /host
        cat /path/to/your/file
        exit
        ```

## How to Verify Compliance Operators are Implemented

The OpenShift Compliance Operator helps you assess and remediate your cluster's compliance with various security benchmarks (e.g., CIS, PCI-DSS).

Here's how to verify its implementation and usage:

1. **Check if the Compliance Operator is Installed:**
    * Verify the operator is deployed in the `openshift-compliance` namespace:

        ```bash
        oc get csv -n openshift-compliance
        # Look for a CSV with a name like "compliance-operator.vX.Y.Z" and "Succeeded" phase.

        oc get deploy -n openshift-compliance
        # Ensure the compliance-operator deployment is Ready.
        ```

    * Check the pods for the Compliance Operator:

        ```bash
        oc get pods -n openshift-compliance
        # Ensure pods related to the compliance-operator are running.
        ```

2. **List Available Compliance Profiles:**
    * The Compliance Operator comes with pre-defined profiles. List them to see what's available:

        ```bash
        oc get profiles.compliance -n openshift-compliance
        ```

        You'll see profiles like `ocp4-cis`, `rhcos4-moderate`, etc. `ocp4-*` profiles target the Kubernetes API, while `rhcos4-*` profiles target the node's operating system.

3. **Check for ScanSettings (How scans run):**
    * ScanSettings define how compliance scans are performed (schedule, storage, roles, etc.).

        ```bash
        oc get scansettings -n openshift-compliance
        oc describe scansetting default -n openshift-compliance # Or any other ScanSetting
        ```

    * You'll typically see a `default` and potentially `default-auto-apply` ScanSetting.

4. **Verify ScanSettingBindings (What profiles are active):**
    * `ScanSettingBinding` objects bind specific compliance profiles to a `ScanSetting`, initiating the actual scans.

        ```bash
        oc get scansettingbinding -n openshift-compliance
        ```

    * If no `ScanSettingBinding` objects exist, then no compliance scans are actively running.

5. **Monitor ComplianceScans and ComplianceSuites:**
    * When a `ScanSettingBinding` is created, the Compliance Operator creates `ComplianceSuite` objects (which represent a set of scans) and `ComplianceScan` objects (individual scans for specific profiles).

        ```bash
        oc get compliancesuite -n openshift-compliance -w
        # Watch the PHASE and RESULT columns. They should eventually go to "DONE" and show a result.

        oc get compliancescan -n openshift-compliance
        # This shows the individual scans and their results.
        ```

    * Look for `ComplianceScan` objects to confirm that scans are running and their `PHASE` and `RESULT`.

6. **Review ComplianceCheckResults:**
    * The most granular results are found in `ComplianceCheckResult` objects. These indicate whether individual checks passed, failed, or were not applicable.

        ```bash
        oc get compliancecheckresult -n openshift-compliance
        # You can filter these by grep-ing for a specific scan name or profile.
        ```

7. **Check Remediation Status (if auto-apply is enabled):**
    * If you have a `ScanSetting` with `autoApplyRemediations: true`, the Compliance Operator will create `ComplianceRemediation` objects to fix non-compliant findings.

        ```bash
        oc get complianceremediation -n openshift-compliance
        ```

8. **Examine Operator Logs for Troubleshooting:**
    * If you suspect issues, check the Compliance Operator's logs:

        ```bash
        oc logs -n openshift-compliance $(oc get pod -n openshift-compliance -l app=compliance-operator -o jsonpath='{.items[0].metadata.name}')
        ```

By following these steps, you can effectively create and implement MachineConfigs to manage your OpenShift nodes' configurations and verify the proper functioning of the Compliance Operator to maintain your cluster's security posture.
