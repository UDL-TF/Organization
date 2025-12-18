# Infrastructure Overview

## Architecture Diagram

```mermaid
graph TB
    subgraph K8S["Kubernetes Cluster"]
        subgraph NODE["node01.udl.tf"]
            SHARED["Shared TF2 Installation<br/>(Host Mount Point)"]

            subgraph SERVER1["UDL.TF | EU | Advanced"]
                POD1["Custom TF2 Image"]
                RESTART1["Restart Controller<br/>(Daily at 04:00)"]
                UPDATE1["Update Controller<br/>(Every 30 min)"]
                POD1 --> RESTART1
                POD1 --> UPDATE1
            end

            subgraph SERVER2["UDL.TF | EU | Advanced #2"]
                POD2["Custom TF2 Image"]
                RESTART2["Restart Controller<br/>(Daily at 04:00)"]
                UPDATE2["Update Controller<br/>(Every 30 min)"]
                POD2 --> RESTART2
                POD2 --> UPDATE2
            end

            subgraph SERVER3["UDL.TF | EU | Normal"]
                POD3["Custom TF2 Image"]
                RESTART3["Restart Controller<br/>(Daily at 04:00)"]
                UPDATE3["Update Controller<br/>(Every 30 min)"]
                POD3 --> RESTART3
                POD3 --> UPDATE3
            end

            POD1 -.->|Mount| SHARED
            POD2 -.->|Mount| SHARED
            POD3 -.->|Mount| SHARED
        end
    end

    style SHARED fill:#e1f5e1
    style NODE fill:#f0f0f0
    style K8S fill:#e3f2fd
```

## Components

### Node

- **node01.udl.tf**: Kubernetes dedicated node that hosts all TF2 servers

### Shared Storage

All TF2 servers mount to the same host installation for:

- Storage efficiency (reduced disk usage)
- Faster caching (shared game files)

### Controllers

Each server runs two CronJob controllers:

- **Restart Controller**: Automatically restarts servers daily at 04:00
- **Update Controller**: Checks for game updates every 30 minutes

### Active Servers

- **UDL.TF | EU | Advanced**: Primary advanced gameplay server
- **UDL.TF | EU | Advanced #2**: Secondary advanced gameplay server
- **UDL.TF | EU | Normal**: Standard gameplay server

## Technical Details

- **Platform**: Kubernetes (k8s)
- **Container Images**: Custom TF2 server images
- **Storage**: Host-mounted shared TF2 installation
- **Automation**: CronJob-based restart and update controllers
