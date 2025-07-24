# Architecture build and run-time

```mermaid
architecture-beta

    group build(server)[Build Environment] 
    group rhel(logos:redhat-icon)[RHEL Server] in build
    service ansible(logos:ansible)[Ansible] in rhel

    group fieldkit(server)[Field Kit Architecture] 
    group ocp(logos:openshift)[OCP Cluster] in fieldkit
    group storage(disk)[Trident Storage] in fieldkit
    group operators[Operators] in ocp
    service git(logos:git-icon)[Git File System] in storage
    service virt(cloud)[Virtualization Operator] in operators
    service gitops(logos:helm)[GitOps Operator] in operators
    service vms(server)[VMs] in ocp

    ansible{group}:R -- L:git{group}
    git{group}:B -- T:gitops{group}
    gitops:R -- L:virt
    virt:B -- T:vms

```
