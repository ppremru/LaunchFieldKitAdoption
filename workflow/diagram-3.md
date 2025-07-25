# 3 - Prepare Deployment Environment

```mermaid
flowchart LR
    subgraph 2[2 - Stage Field Kit Package]
    end
    subgraph 3[3 - Prepare System Controller]
        subgraph Bastion[Setup Bastion Laptop]
          Bastion1[[Fetch RHEL 9 Image]]
          Bastion2[[Install RHEL 9 Image onto SysCon]]
        end
        subgraph Files[Prepare Bastion Files]
          Files1[[Fetch Field Kit Package]]
        end
    end
    subgraph 4[4 - Deploy Field Kit Package]
    end
    Bastion --> Files
    Bastion1 -->Bastion2
    2 -- air gap --> 3 --> 4
```
