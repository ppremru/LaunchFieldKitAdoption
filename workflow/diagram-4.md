# 4 - Deploy Field Kit

```mermaid
---
config:
  theme: 'base'
  themeVariables:
    primaryColor: '#FFFFFFFF'
    primaryTextColor: '#000000'
    primaryBorderColor: '#0c0909ff'
    clusterBkg: '#80808080'
    lineColor: '#0e0d0dff'
    secondaryColor: '#80808080'
---
flowchart LR
    subgraph 3[Prepare Bastion Host]
    end
    subgraph 4[**Deploy Field Kit**]
        subgraph Artifacts[Components]
          direction LR
          subgraph OCP[OCP Disconnected Install]
            direction TB
            OCP1(image registry)
            OCP2(OC Binaries)
            OCP1 ~~~ OCP2
          end
          subgraph Config[Ansible Configuration]
            direction TB
            C1(Modified Variable Files)
          end
          subgraph Collections[Ansible Collections]
            direction TB
            C2(Static Ansible)
          end
          Config ~~~ Collections ~~~ OCP
        end
        subgraph Deploy[Ansible Automation]
          direction LR
          d0[[Create GitOps Repo]]

          subgraph hello[OCP Disconnected Install]
            d1[[Generate CA Certs]]
            d2[[Install]]
            d3[[Monitor]]
            d4[[Post Configure]]
          end 
          d0 --> d1 --> d2 --> d3 --> d4
        end
        subgraph GitOps[GitOps Repo]
          direction LR
          g1[Security]
          g2[Networking]
          g3[Storage]
          g4[Operators]
          g5[Helm Charts]
          g1 ~~~ g2 ~~~ g3 ~~~ g4 ~~~ g5
        end 
        subgraph OCPCluster[OCP Cluster]
          direction LR
          o1[Virt]
          o2[GitOps]
          o3[NMState]
          o4[Migration Toolkit]
          o5[Compliance]
          o1 ~~~ o2 ~~~ o3 ~~~ o4 ~~~ o5
        end
        Artifacts -- input --> Deploy
        GitOps --> OCPCluster
        Deploy -- output --> GitOps
        Deploy -- output --> OCPCluster
    end
    subgraph 5[Verify Field Kit]
    end
    3 -- Prepared Components --> 4 --> 5
```

## Summary

This diagram provides a detailed breakdown of the Deploy Field Kit phase, which is step four in the overall workflow. It outlines the components used for deployment, the automation process, and the final outcomes.

The deployment process begins with three **components** that were produced from the prepare bastion step:

1. **OCP Disconnected Install:** This consists of the necessary binaries and an image registry to perform an offline installation of OpenShift.

2. **Ansible Configuration:** This includes the modified variable files from the previous step, which contain site-specific information.

3. **Ansible Collections:** A static set of Ansible roles and collections used for the automation tasks.

These components are used as input for the **Ansible Automation process**. This automation begins by creating a GitOps repository, followed by a series of steps to install OpenShift in a disconnected environment: generating certificates, performing the installation, monitoring the progress, and post-configuration.  

The automation process produces two main outputs:

1. **GitOps Repository**: The deployment creates a GitOps repository that contains configurations for various cluster functions like security, networking, storage, operators, and Helm charts.  *(Note: the modified variable files are consumed by the ansible playbooks to produce site specific configuration files such as helm charts and stored in the repository.)*

2. **OCP Cluster**: The automation also installs and configures several operators on the OpenShift cluster, including Virtualization, GitOps, NMState, Migration Toolkit, and Compliance.

Finally, after the deployment is complete, the process moves to the Verify Field Kit stage.
