# Kubernetes Services, Load Balancing & Networking - Day 35 Notes

## 📌 Cornell Notes Format

| **Key Points** | **Detailed Notes** | **Summary & Recall Cues** |
|--------------|----------------|----------------------|
| **Why Do We Need Services in Kubernetes?** | - In Kubernetes, Pods are ephemeral, meaning their IP addresses change when they restart.<br>- Without a Service, clients would lose connection when the Pod IP changes.<br>- Services provide a stable endpoint for accessing applications inside a Kubernetes cluster. | Services ensure consistent connectivity to applications. |
| **Types of Kubernetes Services** | - **ClusterIP**: Exposes service internally within the cluster.<br>- **NodePort**: Exposes service on a static port on each node.<br>- **LoadBalancer**: Exposes service externally using cloud provider’s load balancer. | Choose service type based on access needs. |
| **How Services Work?** | - Services use **labels and selectors** to keep track of Pods.<br>- Kubernetes assigns a **stable IP and DNS name** to each Service.<br>- Uses `kube-proxy` for forwarding requests to available Pods. | Services use labels to track and route traffic efficiently. |
| **Load Balancing in Kubernetes** | - Services distribute traffic across multiple Pods to prevent overload.<br>- Ensures high availability and scalability of applications.<br>- Load balancing happens automatically with `kube-proxy`. | Load balancing prevents single-point failures and distributes traffic. |
| **Service Discovery Mechanism** | - Kubernetes maintains an internal DNS (`service-name.namespace.svc.cluster.local`).<br>- Applications query DNS instead of using direct IPs.<br>- Ensures seamless discovery of services within the cluster. | Service discovery automates communication between microservices. |

## 🧠 Mind Map (ASCII Representation)

```
Kubernetes Services
├── Purpose
│   ├── Provide stable networking
│   ├── Handle dynamic Pod IPs
├── Types
│   ├── ClusterIP (Internal access only)
│   ├── NodePort (Exposes service on node port)
│   ├── LoadBalancer (External access via cloud LB)
├── Components
│   ├── Labels & Selectors (Track Pods)
│   ├── Kube-proxy (Manages network traffic)
│   ├── Service DNS (Automatic discovery)
├── Benefits
│   ├── Load balancing
│   ├── Service discovery
│   ├── External exposure
```

## 🔄 Flowchart: How Kubernetes Services Work

```
        Start
          │
          ▼
  Deploy Pods in Kubernetes
          │
          ▼
  Assign Labels to Pods
          │
          ▼
  Create a Service with Selectors
          │
          ▼
  Service Tracks Matching Pods
          │
          ▼
  Requests Routed to Available Pods
          │
          ▼
  Load Balancing Ensures Even Traffic Distribution
          │
          ▼
        End
```

## 🏆 Feature Comparison Table

| Service Type  | Internal Access | External Access | Load Balancing | Use Case |
|--------------|----------------|----------------|---------------|---------|
| **ClusterIP** | ✅ | ❌ | ✅ | Internal communication within cluster |
| **NodePort** | ✅ | ✅ (via Node IP + Port) | ❌ | Access service within organization |
| **LoadBalancer** | ✅ | ✅ (via Cloud LB) | ✅ | Public-facing applications |

## ❓ Interview Q&A (Active Recall)

**Q1: Why are Services needed in Kubernetes?**  
A: Services provide a stable endpoint for accessing applications, handling dynamic Pod IP changes, and enabling load balancing.

**Q2: What are the three main types of Services in Kubernetes?**  
A: ClusterIP (internal access), NodePort (static node port exposure), and LoadBalancer (external access via cloud provider).

**Q3: How does Service Discovery work in Kubernetes?**  
A: Kubernetes assigns DNS names (`service-name.namespace.svc.cluster.local`) for automatic service lookup.

**Q4: How does a Kubernetes Service perform load balancing?**  
A: It distributes traffic across available Pods using `kube-proxy`, ensuring high availability.

## ⚙️ Creating and Managing Kubernetes Services

### Create a ClusterIP Service (Internal Only)
```yaml
# cluster-ip-service.yaml
apiVersion: v1
kind: Service
metadata:
  name: my-clusterip-service
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
```
```bash
kubectl apply -f cluster-ip-service.yaml
kubectl get services
```

### Create a NodePort Service (Accessible via Node IP + Port)
```yaml
# nodeport-service.yaml
apiVersion: v1
kind: Service
metadata:
  name: my-nodeport-service
spec:
  type: NodePort
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
      nodePort: 30007
```
```bash
kubectl apply -f nodeport-service.yaml
kubectl get services
```

### Create a LoadBalancer Service (External Access via Cloud Provider)
```yaml
# loadbalancer-service.yaml
apiVersion: v1
kind: Service
metadata:
  name: my-loadbalancer-service
spec:
  type: LoadBalancer
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
```
```bash
kubectl apply -f loadbalancer-service.yaml
kubectl get services
```

## 🎯 Key Takeaways
- Kubernetes Services provide stable networking and solve the issue of dynamic Pod IPs.
- ClusterIP is the default service type, used for internal communication.
- NodePort allows access from outside the cluster using a node’s IP and port.
- LoadBalancer exposes services externally using a cloud provider’s load balancer.
- Services use labels and selectors to dynamically track and route traffic to Pods.
- Kubernetes automatically assigns DNS names for service discovery.

---
This Markdown file integrates **Cornell notes, mind maps, flowcharts, tables, Q&A, and structured guides** to maximize learning and recall efficiency. 🚀
