# Grafana Dashboards

This repository contains a curated collection of Grafana dashboards developed to enhance observability in Kubernetes clusters. The dashboards provide insights into certificate management, security vulnerabilities, and container log analysis, using tools like `cert-manager`, `Trivy`, and `Loki`.

> ⚠️ **Disclaimer**  
> I am not the original creator of these dashboards. These dashboards were sourced from public repositories and community resources, then modified to suit my own home lab and personal monitoring needs. Credit belongs to the original authors.

---

## Dashboards Overview

### 1. **Certificate_Dashboard.json**
A focused dashboard displaying the health and status of TLS certificates managed by `cert-manager`.

- ✅ Ready Certificates  
- ⏳ Pending Certificates  
- ❌ Failed Certificates  
- ⌛ Certificates Expiring in <30 Days  
- 📊 Expiration Breakdown by Certificate  

Useful for tracking cert lifespans and automation success in production clusters.

---

### 2. **CertManager_Extended_Dashboard.json**
An enhanced version of the certificate dashboard with extended insights and improved visuals.

- Adds granular expiration details  
- Displays cert states with Prometheus metrics  
- Useful for environments with multiple cert issuers or namespaces

---

### 3. **Trivy Operator Dashboard.json**
Visualizes security findings from the [Trivy Operator](https://github.com/aquasecurity/trivy-operator).

- 🔍 Misconfigurations, exposed secrets, and RBAC issues  
- 📊 Vulnerability count by severity (Critical, High, Medium, Low, Unknown)  
- 📈 Time series of vulnerabilities by namespace  

---

### 4. **Trivy Operator Reports.json**
Simplified summary dashboard that aggregates vulnerability metrics by severity.

- Bar and area charts for:  
  - LOW, MEDIUM, HIGH, CRITICAL, UNKNOWN vulnerabilities  
  - Total count over time  
- Good for executive summaries or red/yellow/green risk reporting

---

### 5. **Trivy Vulnerabilities.json**
A specialized dashboard intended for use with the [Kube Trivy Exporter](https://github.com/kaidotdev/kube-trivy-exporter).

- Gauge visualizations per severity level  
- Lightweight and ideal for alert-based dashboards  
- Companion to Grafana dashboard ID `12330`

---

### 6. **Kubernetes_log_from_Loki.json**
A general-purpose log search dashboard backed by [Loki](https://grafana.com/oss/loki/).

- 🔎 Query by namespace/pod and free-text search  
- 📈 Timeseries log frequency panel  
- 📄 Log viewer with wrap, sort, and filter options  

---

### 7. **Loki_Kubernetes_Logs.json**
Another Loki-backed dashboard with more advanced templating and visual customizations.

- 📄 Log stream by namespace, container, and stream type  
- 💡 Includes dynamic search input and templated filtering  
- Great for troubleshooting specific microservices

---

## Getting Started

1. Install [Grafana](https://grafana.com/grafana/download) and your preferred data sources (Prometheus, Loki).
2. Import dashboards from JSON via the Grafana UI or API.
3. Adjust data source UIDs in the JSON if necessary.

---

## Requirements

- Grafana 9.x+ or 10.x recommended  
- Prometheus for cert-manager and Trivy metrics  
- Loki for Kubernetes logs  
- Trivy Operator (for vulnerability and config metrics)

---

## Contributing

Feel free to open issues or submit pull requests to improve dashboard queries, layouts, or add new use cases.

---

## License

MIT License

