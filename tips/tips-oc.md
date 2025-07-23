# Tips for oc

Here's a short OpenShift (OCP) cheat sheet for new users, focusing on common `oc` commands:

-----

## OpenShift (OCP) `oc` Command Cheat Sheet for New Users

This cheat sheet provides a quick reference for essential `oc` commands to help you navigate and interact with OpenShift.

**1. Login & Context**

  * **Login to OpenShift:**
    ```bash
    oc login --token=<your_token> --server=<your_api_url>
    ```
    *(Often, your admin will provide the full `oc login` command.)*
  * **Check current user and project:**
    ```bash
    oc whoami
    ```
  * **List available projects/namespaces:**
    ```bash
    oc get projects
    oc projects # Shorthand for listing and changing
    ```
  * **Switch to a different project:**
    ```bash
    oc project <project_name>
    ```

**2. Viewing Resources**

  * **Get all resources in the current project:**
    ```bash
    oc get all
    ```
  * **List specific resource types (e.g., pods, deployments, services):**
    ```bash
    oc get pods
    oc get deployments
    oc get svc # Short for services
    oc get routes
    ```
  * **Get detailed information about a resource:**
    ```bash
    oc describe pod <pod_name>
    oc describe deployment <deployment_name>
    ```
  * **View logs from a pod:**
    ```bash
    oc logs <pod_name>
    oc logs -f <pod_name> # Follow logs (like tail -f)
    ```

**3. Interacting with Resources**

  * **Execute a command inside a pod:**
    ```bash
    oc rsh <pod_name> <command> # e.g., oc rsh my-app-pod ls -l
    oc rsh <pod_name> bash # Get a shell inside the pod
    ```
  * **Port-forward from a pod to your local machine:**
    ```bash
    oc port-forward <pod_name> <local_port>:<pod_port>
    ```
    *(Useful for accessing services directly from your local browser/tools)*
  * **Scale a deployment:**
    ```bash
    oc scale deployment <deployment_name> --replicas=<number>
    ```
  * **Delete a resource:**
    ```bash
    oc delete pod <pod_name>
    oc delete deployment <deployment_name>
    oc delete all --selector app=<app_label> # Delete all resources with a specific label
    ```
    **CAUTION: `oc delete` is permanent\!**

**4. Creating & Applying Resources (Advanced/Admin)**

  * **Apply a YAML/JSON configuration file:**
    ```bash
    oc apply -f <filename.yaml>
    ```
  * **Create resources directly from the command line (less common for complex apps):**
    ```bash
    oc new-app --name=my-app <image_name> # Create a new application from an image
    oc expose svc <service_name> # Expose a service via a route
    ```

**5. Troubleshooting & Debugging**

  * **View events in the current project:**
    ```bash
    oc get events
    ```
  * **Get the status of your cluster (for admins):**
    ```bash
    oc status
    ```

-----

**Tips for New Users:**

  * **Use `oc get <resource_type> -o wide`** for more detailed output (e.g., IP addresses, node names).
  * **Use `oc get <resource_type> -w`** to watch for changes to resources.
  * **Tab completion:** Set up `oc` tab completion in your shell (refer to OpenShift documentation for your specific shell).
  * **Official Documentation:** The OpenShift documentation is your best friend for in-depth information.
  * **Don't be afraid to `oc describe`\!** It provides a wealth of information about a resource's state and configuration.

This cheat sheet should give new users a solid foundation for interacting with OpenShift using the `oc` command-line tool.
