# Kubernetes Architecture Notes 🏗️

## 📌 Cornell Method

| **Cue (Keywords/Questions)** | **Notes (Detailed Explanation)** |
|------------------------------|----------------------------------|
| Why is Kubernetes called K8s? | It’s a shorthand for "Kubernetes" where "K" and "s" remain, and the 8 letters in between are replaced with "8". |
| Difference between Docker & Kubernetes? | Kubernetes provides clustering, auto-healing, auto-scaling, and enterprise-level support like advanced networking and load balancing. |
| What are the main components of Kubernetes? | Kubernetes is divided into **Control Plane** and **Data Plane**. The Control Plane has API Server, Scheduler, etcd, Controller Manager, and Cloud Controller Manager. The Data Plane has Kubelet, Kube Proxy, and Container Runtime. |
| Role of API Server? | Acts as the main interface for Kubernetes, processing external requests and directing them. |

---

## 🧠 Mind Map (Text Representation)
```plaintext
Kubernetes Architecture
│
├── Control Plane (Master Node)
│   ├── API Server → Handles all requests
│   ├── Scheduler → Assigns pods to nodes
│   ├── etcd → Stores cluster state
│   ├── Controller Manager → Ensures system health
│   ├── Cloud Controller Manager → Manages cloud integration
│
└── Data Plane (Worker Nodes)
    ├── Kubelet → Ensures pods are running
    ├── Kube Proxy → Manages networking & load balancing
    ├── Container Runtime → Runs containers (Docker, containerd, CRI-O)
```

---

## 📊 Comparison Table

| **Feature**       | **Docker**           | **Kubernetes**         |
|------------------|--------------------|----------------------|
| Unit of Deployment | Container | Pod (Multiple Containers) |
| Scaling | Manual | Auto-scaling |
| Networking | Simple bridge network | Advanced networking via Kube Proxy |
| Load Balancing | External tool needed | Built-in |

---

## 📜 Flowchart for Kubernetes Deployment
```plaintext
User → API Server → Scheduler → etcd (Stores state)
                          ↓
                     Assigns to Worker Node
                          ↓
               Kubelet → Starts Pod
               Kube Proxy → Manages Networking
               Container Runtime → Runs Container
```

---

## 🎯 Summary (Bullet Points)

- **Kubernetes vs Docker** → Kubernetes provides clustering, auto-healing, and scalability.
- **Two Main Components** → Control Plane (manages clusters) and Data Plane (runs workloads).
- **Important Control Plane Components**:
  - **API Server** → Gateway to Kubernetes, processes external requests.
  - **Scheduler** → Assigns workloads to worker nodes based on resource availability.
  - **etcd** → Stores the cluster’s configuration and state as key-value pairs.
  - **Controller Manager** → Ensures the desired state of the cluster by managing controllers like ReplicaSet.
  - **Cloud Controller Manager** → Integrates Kubernetes with cloud providers for storage, networking, and load balancing.
- **Worker Node Components**:
  - **Kubelet** → Ensures pods are running.
  - **Kube Proxy** → Manages networking.
  - **Container Runtime** → Runs the actual containers.

---

## ✏️ Assignment & Next Steps

- **Draw a diagram** explaining Kubernetes architecture.
- **Summarize in your own words** and post it on GitHub/LinkedIn.
- **Prepare for an interview** by practicing answers based on this structure.

---

This structured note-taking approach combines **Cornell Notes, Mind Maps, Flowcharts, Tables, and Bullet Points** for a better understanding. 🚀
