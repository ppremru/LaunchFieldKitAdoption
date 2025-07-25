# High Level Architecture

## Build and Runtime

```mermaid
architecture-beta

    group build[Build Environment] 
       service repos[Git Repos] in build
       service pipelines[Pipelines] in build
       service package[Package] in build
       repos:B -- T:pipelines
       pipelines:B -- T: package
    group airgap[Air Gap]
       service stage[Stage] in airgap
    group fieldkit[Field Kit Environment]
        group rhel[Bastion RHEL Server] in fieldkit
            service ansible[Ansible] in rhel
        group storage[Storage] in fieldkit
            service repofile[Git File System] in storage
        group ocp[Disconnected OCP Cluster] in fieldkit
            service gitops[GitOps Operator] in ocp
            service virt[Virtualization Operator] in ocp
            service vms[VMs] in ocp
            gitops:B -- T:virt
            virt:B -- T:vms
        repofile:B -- T:gitops{group}
    package{group}:R -- L:stage{group}
    stage{group}:R -- L:ansible{group}
    ansible{group}:R -- L:repofile{group}
    ansible{group}:B -- L:gitops{group}
  ```