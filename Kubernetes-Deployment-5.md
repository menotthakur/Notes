# Kubernetes Deployment & ReplicaSets - Day 34 Notes

## 📌 Cornell Notes Format

| **Key Points** | **Detailed Notes** | **Summary & Recall Cues** |
|--------------|----------------|----------------------|
| **Containers vs. Pods vs. Deployments** | - Containers are individual runtime environments.<br>- Pods group one or more containers and share networking & storage.<br>- Deployments manage and scale multiple Pods. | Deployment ensures high availability and scaling. |
| **Why Use Deployments?** | - Provides auto-healing and auto-scaling.<br>- Allows rolling updates and zero downtime deployments.<br>- Uses ReplicaSets to ensure desired Pod count. | Deployments improve reliability & uptime. |
| **ReplicaSets & Their Role** | - Ensures the desired number of Pod replicas run.<br>- If a Pod is deleted, ReplicaSet recreates it automatically.<br>- Works with Deployments to maintain cluster state. | ReplicaSets guarantee availability & redundancy. |
| **Deployment YAML Example** | - Defined in YAML format.<br>- Specifies the number of replicas, container image, ports, etc.<br>- Managed using `kubectl apply -f deployment.yaml`. | YAML defines Kubernetes resources declaratively. |

## 🧠 Mind Map (ASCII Representation)

```
Kubernetes Deployment
├── Containers
│   ├── Run standalone
│   ├── Managed via Pods
├── Pods
│   ├── Group containers
│   ├── Share networking/storage
├── Deployments
│   ├── Manage multiple Pods
│   ├── Use ReplicaSets for auto-scaling
│   ├── Ensure high availability
├── ReplicaSets
│   ├── Maintain desired number of Pods
│   ├── Handle Pod failures automatically
```

## 🔄 Flowchart: Kubernetes Deployment Workflow

```
        Start
          │
          ▼
  Create Deployment (YAML Spec)
          │
          ▼
  Deploy using kubectl apply -f deployment.yaml
          │
          ▼
  ReplicaSet ensures desired Pods are running
          │
          ▼
  Auto-healing: If a Pod fails, ReplicaSet creates a new one
          │
          ▼
  Auto-scaling: Adjust replicas dynamically
          │
          ▼
        End
```

## 🏆 Feature Comparison Table

| Feature        | Container | Pod | Deployment |
|---------------|----------|-----|------------|
| **Unit of Deployment** | Individual | Grouped Containers | Managed Pods |
| **Networking** | Separate per container | Shared in a Pod | Managed across cluster |
| **Scaling** | Manual | Fixed | Auto-scalable |
| **Self-healing** | No | No | Yes |
| **Zero Downtime Updates** | No | No | Yes |

## ❓ Interview Q&A (Active Recall)

**Q1: What is the difference between a container, a Pod, and a Deployment?**  
A: Containers are standalone runtime environments, Pods group containers with shared networking and storage, and Deployments manage multiple Pods with auto-scaling and auto-healing features.

**Q2: Why should you use a Deployment instead of just a Pod?**  
A: Deployments provide auto-healing, auto-scaling, and zero-downtime updates, which Pods alone cannot achieve.

**Q3: What is the role of a ReplicaSet in Kubernetes?**  
A: A ReplicaSet ensures the desired number of Pods run at all times, recreating Pods if they fail or are deleted.

**Q4: How do you create and update a Deployment in Kubernetes?**  
A: Write a YAML definition and apply it using `kubectl apply -f deployment.yaml`. Update the YAML and reapply it for changes.

## ⚙️ Installing and Deploying a Kubernetes Deployment

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

### Create and Deploy a Kubernetes Deployment
```yaml
# deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

```bash
# Apply the deployment definition
kubectl apply -f deployment.yaml

# Check deployment status
kubectl get deployments

# Describe deployment details
kubectl describe deployment nginx-deployment

# Scale the deployment to 5 replicas
kubectl scale deployment nginx-deployment --replicas=5

# Delete the deployment
kubectl delete deployment nginx-deployment
```

## 🎯 Key Takeaways
- Deployments manage Pods and ensure high availability.
- ReplicaSets maintain the desired number of Pods.
- Deployments provide auto-scaling and zero-downtime updates.
- `kubectl apply` is used to create and update Deployments.
- Always use Deployments instead of standalone Pods in production.

---
This Markdown file integrates **Cornell notes, mind maps, flowcharts, tables, Q&A, and structured guides** to maximize learning and recall efficiency. 🚀
