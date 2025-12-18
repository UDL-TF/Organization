# Infrastructure Overview

## Architecture Diagram

```mermaid
graph TB
    subgraph K8S["Kubernetes Cluster"]
        subgraph NODE["node01.udl.tf"]
            SHARED["Shared TF2 Installation<br/>(Host Mount Point)"]

            RESTART["Restart Controller<br/>(CronJob: Daily at 04:00)"]
            UPDATE["Update Controller<br/>(CronJob: Every 30 min)"]

            subgraph SERVER1["UDL.TF | EU | Advanced"]
                POD1["Custom TF2 Image"]
            end

            subgraph SERVER2["UDL.TF | EU | Advanced #2"]
                POD2["Custom TF2 Image"]
            end

            subgraph SERVER3["UDL.TF | EU | Normal"]
                POD3["Custom TF2 Image"]
            end

            RESTART --> POD1
            RESTART --> POD2
            RESTART --> POD3

            UPDATE --> POD1
            UPDATE --> POD2
            UPDATE --> POD3

            POD1 -.->|Mount| SHARED
            POD2 -.->|Mount| SHARED
            POD3 -.->|Mount| SHARED
        end
    end

    style SHARED fill:#1a4d2e,stroke:#4ade80,stroke-width:2px,color:#fff
    style NODE fill:#1e293b,stroke:#64748b,stroke-width:2px,color:#fff
    style K8S fill:#1e3a8a,stroke:#60a5fa,stroke-width:2px,color:#fff
    style RESTART fill:#7c2d12,stroke:#fb923c,stroke-width:2px,color:#fff
    style UPDATE fill:#581c87,stroke:#c084fc,stroke-width:2px,color:#fff
```

## Components

### Node

- **node01.udl.tf**: Kubernetes dedicated node that hosts all TF2 servers

### Shared Storage

All TF2 servers mount to the same host installation for:

- Storage efficiency (reduced disk usage)
- Faster caching (shared game files)

### Controllers

Two CronJob controllers manage all servers:

- **Restart Controller**: Automatically restarts all servers daily at 04:00
- **Update Controller**: Checks for game updates every 30 minutes and updates all servers as needed

### Active Servers

- **UDL.TF | EU | Advanced**: Primary advanced gameplay server
- **UDL.TF | EU | Advanced #2**: Secondary advanced gameplay server
- **UDL.TF | EU | Normal**: Standard gameplay server

## Technical Details

- **Platform**: Kubernetes (k8s)
- **Container Images**: Custom TF2 server images
- **Storage**: Host-mounted shared TF2 installation
- **Automation**: CronJob-based restart and update controllers
