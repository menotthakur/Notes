# Observability Fundamentals - Detailed Notes

## **1. Overview of Observability**
Observability helps in understanding the internal state of a system based on external outputs.

### **Key Topics:**
- **What is Observability?**
- **Why do we need Observability?**
- **Three Pillars of Observability**
- **Difference between Observability and Monitoring**
- **Observability Tools**

## **2. The Three Pillars of Observability**  
Observability is built on three primary components:

| Pillar | Description |
|--------|-------------|
| **Metrics** | Numerical data representing system health (CPU usage, memory, response time) |
| **Logs** | Textual records of system activities (debugging and error tracing) |
| **Traces** | End-to-end tracking of a request flow through a system |

---

## **3. Observability vs. Monitoring (Cornell Method)**

| **Concept** | **Observability** | **Monitoring** |
|-------------|----------------|------------|
| **Definition** | Understanding the internal system state by analyzing external outputs | Tracking system health using pre-defined parameters |
| **Scope** | Includes metrics, logs, traces | Mainly deals with metrics and dashboards |
| **Purpose** | Helps diagnose and solve issues | Alerts when a problem occurs |
| **Example** | Identifying why API latency increased | Checking if CPU usage exceeded 80% |

---

## **4. How Observability Works (Flowchart)**
```
User Request → Load Balancer → Frontend App → Backend App → Database
            ↓               ↓                   ↓                  ↓
          Metrics       Logs            Logs + Traces        Logs + Traces
            ↓               ↓                   ↓                  ↓
       Monitoring    Debugging       Root Cause         Performance
```
---

## **5. Key Observability Tools**

| **Component** | **Tool** |
|--------------|---------|
| **Metrics** | Prometheus, Datadog, CloudWatch |
| **Logs** | EFK (Elasticsearch, Fluentbit, Kibana), Loki |
| **Tracing** | Jaeger, OpenTelemetry |

---

## **6. Example Use Case (Flashcards Format)**

**Q:** What is an example of observability in action?  
**A:** Identifying why a banking application request takes 20s instead of 5s using logs and traces.

**Q:** How does logging help in debugging?  
**A:** It records detailed error messages and helps pinpoint the issue.

**Q:** What is OpenTelemetry?  
**A:** A set of APIs & SDKs for collecting telemetry data (metrics, logs, traces).

---

## **7. Real-World Scenario**
Imagine a Resume Builder application deployed on Kubernetes. The company promises 99.9% uptime (SLA). Observability helps:
- **Metrics** track uptime and request latency.
- **Logs** identify API errors.
- **Traces** track request failures.

With observability, the company can detect & fix failures before they impact customers.

---

## **8. Responsibilities: Developer vs. DevOps**

| **Task** | **Developer** | **DevOps** |
|----------|-------------|---------|
| **Instrument Metrics & Logs** | ✅ | ❌ |
| **Set Up Monitoring Stack** | ❌ | ✅ |
| **Configure Alerts & Dashboards** | ❌ | ✅ |

---

## **9. Summary (Cheat Sheet)**
- Observability helps **understand what, why, and how** issues occur.
- Three pillars: **Metrics, Logs, Traces**.
- Monitoring is a subset of Observability.
- **Key tools:** Prometheus (Metrics), EFK (Logs), Jaeger (Traces).
- Observability ensures **better uptime, debugging, and performance monitoring**.

### **Revision Tips:**
- Use the Cornell notes for structured learning.
- Refer to flowcharts to understand data flow.
- Revise flashcards for quick memory recall.
- Read real-world examples to relate concepts.

