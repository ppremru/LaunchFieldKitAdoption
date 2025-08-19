# About Field-Kit Solution Architecture

## Field Kit Architecture

This Architecture Overview diagram outlines an air-gapped deployment strategy:

* **Development Environment**  
  The software solution is built and compressed into a "deployment package"
* **Stage Environment**  
The deployment package is securely transferred from development to a staging area.  (The stage could be ISOs copied to media.)
* **Field Kit Environment**  
The field kit consists of a bastion host that will be prepared to deploy the solution from the package.   (The bastion host is most likely a laptop).   The kit consists of multiple servers and storage.

## Field Kit Architecture Diagram

```mermaid
architecture-beta
  group kit[Field Kit Environment]
    service bastion(server)[Bastion Host] in kit
    service top_disk(server)[Cluster Node] in kit
    service bottom_disk(server)[Worker Node 1] in kit
    service top_gateway(server)[Worker Node 2] in kit
    service bottom_gateway(disk)[Storage] in kit

    junction junctionCenter in kit
    junction junctionRight in kit
    bastion:R -- L:junctionCenter
    top_disk:B -- T:junctionCenter
    bottom_disk:T -- B:junctionCenter
    junctionCenter:R -- L:junctionRight
    top_gateway:B -- T:junctionRight
    bottom_gateway:T -- B:junctionRight

  group gap[Stage Environment]
    service stage(server)[Stage] in gap

  group dev[Development Environment]
    service package(disk)[Deployment Package] in dev
    service build(server)[Build Servers] in dev
    service git(disk)[Code Repositories] in dev
 
  git:B -- T:build
  build:B -- T:package
  package{group}:B -- T:stage{group}
  stage{group}:R -- L:bastion{group}
```
