# Kubernetes Pods - Day 33 Notes

## 📌 Cornell Notes Format

| **Key Points** | **Detailed Notes** | **Summary & Recall Cues** |
|--------------|----------------|----------------------|
| **Docker vs. Kubernetes** | - Docker runs containers individually.  
  - Kubernetes manages multiple containers via pods.  
  - Kubernetes provides auto-scaling, self-healing, and enterprise-level support. | Kubernetes is a container orchestrator, not just a container runtime. |
| **What is a Pod?** | - The smallest deployable unit in Kubernetes.  
  - Can contain one or multiple containers.  
  - Containers in a pod share networking and storage. | Pods are a wrapper around containers for better management. |
| **Why Pods Instead of Direct Containers?** | - Provides declarative specifications via YAML.  
  - Enables shared networking and storage among containers in a pod.  
  - Standardizes container deployment. | Pods enable Kubernetes to manage containers effectively. |
| **Installing Kubernetes Locally** | - Use Minikube for local Kubernetes clusters.  
  - Alternatives: K3s, Kind, MicroK8s. | Minikube is the simplest option for local Kubernetes. |
| **Deploying Your First Pod** | - Write a `pod.yaml` specification.  
  - Use `kubectl apply -f pod.yaml`.  
  - Verify using `kubectl get pods`. | Kubernetes pods are created using YAML specifications. |

## 🧠 Mind Map (ASCII Representation)

```
Kubernetes Pods
├── Definition
│   ├── Smallest deployable unit
│   ├── Contains one or multiple containers
│   ├── Shares network/storage
├── Deployment
│   ├── Defined via YAML
│   ├── Created using kubectl
│   ├── Managed by Kubernetes
├── Advantages
│   ├── Auto-scaling
│   ├── Auto-healing
│   ├── Enterprise-level capabilities
```

## 🔄 Flowchart: Pod Lifecycle

```
        Start
          │
          ▼
  Write pod.yaml (YAML Spec)
          │
          ▼
  Apply with kubectl apply -f pod.yaml
          │
          ▼
  Check status with kubectl get pods
          │
          ▼
  Debug with kubectl describe pod <pod-name>
          │
          ▼
  Delete pod with kubectl delete pod <pod-name>
          │
          ▼
        End
```

## 🏆 Feature Comparison Table

| Feature        | Docker | Kubernetes Pod |
|---------------|--------|---------------|
| **Unit of Deployment** | Container | Pod (Group of Containers) |
| **Networking** | Separate for each container | Shared within a pod |
| **Scaling** | Manual | Auto-scaling via deployments |
| **Self-healing** | No | Yes |
| **Storage Sharing** | No | Yes |

## ❓ Interview Q&A (Active Recall)

**Q1: What is a Kubernetes Pod?**  
A: A Pod is the smallest deployable unit in Kubernetes, containing one or more containers that share networking and storage.

**Q2: Why does Kubernetes use Pods instead of standalone containers?**  
A: Pods provide better management, standardization, shared networking, and storage capabilities, making Kubernetes orchestration easier.

**Q3: How do you create a Pod in Kubernetes?**  
A: Write a `pod.yaml` specification and apply it using `kubectl apply -f pod.yaml`.

**Q4: How do you check the status of a running Pod?**  
A: Use `kubectl get pods` and `kubectl describe pod <pod-name>`.

## ⚙️ Installing and Deploying Pods

### Install Minikube (For Local Clusters)
```bash
# Install Minikube (Linux/macOS/Windows)
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start Minikube Cluster
minikube start
```

### Install kubectl
```bash
# Install kubectl (Linux/macOS/Windows)
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install kubectl /usr/local/bin/kubectl

# Check version
kubectl version --client
```

### Create and Deploy a Pod
```yaml
# pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80
```

```bash
# Apply the pod definition
kubectl apply -f pod.yaml

# Check pod status
kubectl get pods

# Describe pod
kubectl describe pod nginx-pod

# Delete pod
kubectl delete pod nginx-pod
```

## 🎯 Key Takeaways
- Kubernetes pods are the basic deployment unit, acting as a wrapper around containers.
- Pods can contain multiple containers that share networking and storage.
- `kubectl` is the primary command-line tool to manage Kubernetes resources.
- Minikube provides an easy way to run Kubernetes locally.
- YAML specifications define pod deployment, ensuring declarative container management.

---

