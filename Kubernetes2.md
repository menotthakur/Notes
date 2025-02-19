# Kubernetes Architecture Notes

## Cornell Method

### Notes

#### Kubernetes Overview
- Kubernetes is a container orchestration platform.
- It provides features like auto-healing, auto-scaling, and advanced networking.

#### Key Components
- **Control Plane**: Manages the Kubernetes cluster.
    - **API Server**: Exposes Kubernetes API.
    - **Scheduler**: Schedules pods on nodes.
    - **etcd**: Key-value store for cluster data.
    - **Controller Manager**: Manages controllers like ReplicaSets.
    - **Cloud Controller Manager**: Integrates with cloud providers.

- **Data Plane**: Executes the workloads.
    - **Kubelet**: Ensures pods are running.
    - **Kube Proxy**: Manages networking and load balancing.
    - **Container Runtime**: Runs containers (e.g., Docker, containerd).

### Cues
- **K8s**: Short for Kubernetes.
- **Pod**: Smallest deployable unit in Kubernetes.
- **Cluster**: Group of nodes managed by Kubernetes.
- **Auto-healing**: Automatically restarts failed pods.
- **Auto-scaling**: Adjusts the number of pod replicas based on demand.

### Summary
Kubernetes architecture consists of a control plane and a data plane. The control plane manages the cluster, while the data plane runs the workloads. Key components include the API server, scheduler, etcd, controller manager, and cloud controller manager in the control plane, and kubelet, kube proxy, and container runtime in the data plane.

## Mind Map

```plaintext
Kubernetes Architecture
├── Control Plane
│   ├── API Server
│   ├── Scheduler
│   ├── etcd
│   ├── Controller Manager
│   └── Cloud Controller Manager
└── Data Plane
        ├── Kubelet
        ├── Kube Proxy
        └── Container Runtime
```

## Table for Comparison

| Component               | Description                                      | Docker Equivalent       |
|-------------------------|--------------------------------------------------|-------------------------|
| API Server              | Exposes Kubernetes API                           | N/A                     |
| Scheduler               | Schedules pods on nodes                          | N/A                     |
| etcd                    | Key-value store for cluster data                 | N/A                     |
| Controller Manager      | Manages controllers like ReplicaSets             | N/A                     |
| Cloud Controller Manager| Integrates with cloud providers                  | N/A                     |
| Kubelet                 | Ensures pods are running                         | Docker Engine           |
| Kube Proxy              | Manages networking and load balancing            | Docker Bridge Networking|
| Container Runtime       | Runs containers (e.g., Docker, containerd)       | Docker Shim             |

## Detailed Notes

### Kubernetes Control Plane
- **API Server**: The core component that exposes the Kubernetes API to the external world. It handles all the incoming requests.
- **Scheduler**: Responsible for scheduling pods on nodes based on resource availability.
- **etcd**: A distributed key-value store that holds all the cluster data.
- **Controller Manager**: Manages various controllers that ensure the desired state of the cluster, such as ReplicaSets.
- **Cloud Controller Manager**: Integrates Kubernetes with cloud providers, allowing it to manage cloud-specific resources like load balancers and storage.

### Kubernetes Data Plane
- **Kubelet**: An agent that runs on each node in the cluster. It ensures that containers are running in a pod.
- **Kube Proxy**: Manages network rules on nodes. It provides networking and load balancing for services.
- **Container Runtime**: The software responsible for running containers. Kubernetes supports multiple container runtimes, including Docker, containerd, and CRI-O.

### Key Concepts
- **Pod**: The smallest deployable unit in Kubernetes, which can contain one or more containers.
- **Cluster**: A set of nodes managed by Kubernetes.
- **Auto-healing**: Kubernetes automatically restarts failed pods to maintain the desired state.
- **Auto-scaling**: Kubernetes adjusts the number of pod replicas based on the current load.

### Practical Example
1. **Creating a Container in Docker**:
     - Command: `docker run`
     - Requires Docker Engine and Docker Shim.

2. **Creating a Pod in Kubernetes**:
     - Command: `kubectl apply -f pod.yaml`
     - Involves API Server, Scheduler, Kubelet, and Container Runtime.

### Conclusion
Understanding the architecture of Kubernetes is crucial for managing containerized applications at scale. The control plane components manage the cluster, while the data plane components run the workloads. Kubernetes provides advanced features like auto-healing and auto-scaling, making it a powerful tool for modern application deployment.
