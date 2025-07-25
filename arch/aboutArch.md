# About Field-Kit Solution Architecture

## Overview

[Architecture Overview](./diagram-arch.md)

This Architecture Overview diagram outlines an air-gapped deployment strategy where a software package built in an isolated environment is securely transferred to a RHEL bastion host, equipped with Ansible.  The package contains ansible playbooks and collections which orchestrates the deployment and configuration of an OpenShift cluster. The cluster then leverages GitOps principles, using a local Git file system (populated by Ansible), to manage its own state, including the deployment and lifecycle of virtual machines through the OpenShift Virtualization Operator.

### Overall Flow

The diagram illustrates a process where a "Package" created in a "Build Environment" is transferred across an "Air Gap" to a "Field Kit Environment." Within the Field Kit, an Ansible-enabled RHEL Bastion Server uses this package (indirectly) to set up the environment and interact with an OpenShift cluster, which then uses GitOps to manage virtual machines:

Groups and Services:

* **Build Environment**: Represents the initial stages where software artifacts are created.
  * **Git Repositories**:  Stores the source code and configuration file templates.
  * **Pipelines**: Processes (e.g., CI/CD pipelines or manual) that consume content from Git Repos and output a package.
  * **Package**: Contains the ansible plays and the artifacts that will be used to generate the OCP cluster for virtualization.
* **Air Gap**: Signifies a secure, isolated zone
  * **Stage**: Area within the air gap is where the package is temporarily held after being transferred from the Build Environment; ready to be picked up by the bastion host.
* **Field Kit Environment**: This is the remote (edge) deployment target, an isolated hardware stack.
  * **Bastion RHEL Server**: A dedicated Red Hat Enterprise Linux server acting as a secure jump host within the Field Kit.
    * **Ansible**: The automation engine installed directly on the RHEL bastion, responsible for orchestrating deployments and configurations.
  * **Storage**: Represents the storage components within the Field Kit.
    * **Git File System** : A local copy of a Git repository containing OCP configuration files and Helm Charts.  . This acts as the source of truth for the GitOps operator.
  * **OCP Cluster**: The deployed OpenShift Container Platform environment.
    * **GitOps Operator**: An OpenShift operator that continuously monitors the Git File System (or a similar Git repository) for changes and automatically applies those changes to the cluster, ensuring the desired state.
    * **Virtualization Operator**: An OpenShift operator that enables running virtual machines directly on the OpenShift cluster.
    * **VMs** : The actual virtual machines running within the OCP cluster, managed by the Virtualization Operator.
