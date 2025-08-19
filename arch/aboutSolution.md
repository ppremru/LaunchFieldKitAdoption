# About Field-Kit Solution 

## Which Products are in the Field Kit Solution Stack?

The *Field-Kit* technology stack contains the following **Red Hat** products:

1. Red Hat Enterprise Linux (RHEL)
2. Ansible
3. OpenShift Container Platform (OCP)
4. OpenShift Virtualization (OCP-Virt)

## Field Kit Solution Architecture

```mermaid
---
config:
  theme: 'base'
  themeVariables:
    primaryColor: '#FFFFFFFF'
    primaryTextColor: '#000000'
    primaryBorderColor: '#0c0909ff'
    clusterBkg: '#FFFFFFFF'
    lineColor: '#000000'
    secondaryColor: '#80808080'
---
flowchart LR
    subgraph RH[**Red Hat Product Stack**]
            direction TB
            subgraph RHEL[RHEL]
              Ansible[Ansible]
            end
            subgraph OCP[OpenShift Platform]
              Virt[OCP Virtualization]
            end
            Ansible -- Installs Platform --> OCP
            Ansible -- Configures Operators --> OCP
    end
    style RH stroke:#000000;
    style RHEL stroke:#FF0000;
    style OCP stroke:#FF0000;
    style Virt stroke:#FF0000;
    style Ansible stroke:#FF0000;
```