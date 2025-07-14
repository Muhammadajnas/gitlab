# 🚀 GitLab Helm Chart for Local MicroK8s Deployment

This Helm chart provides a simple and customizable way to deploy **GitLab Community Edition (CE)** on a local Kubernetes cluster using **MicroK8s**, without relying on the official GitLab Helm chart.

It is ideal for developers and DevOps engineers who want a lightweight, local GitLab setup for testing and experimentation.

---

## 📂 Project Structure

gitlab-helm-chart/
├── Chart.yaml # Metadata about the chart
├── values.yaml # Configurable values (image, storage, ingress, etc.)
└── templates/ # Kubernetes manifest templates
├── deployment.yaml # GitLab deployment with volume and environment config
├── service.yaml # Exposes GitLab via ClusterIP
├── ingress.yaml # Optional Ingress rule for domain-based access
└── pvc.yaml # PersistentVolumeClaim for data storage



---

## ⚙️ Prerequisites

- [MicroK8s](https://microk8s.io/) installed and running
- [Helm 3](https://helm.sh/docs/intro/install/) installed
- Internet access to pull GitLab CE Docker images
- (Optional) DNS or `/etc/hosts` entry for `gitlab.local`

---

## 🚀 Deployment

### 1. Enable Required MicroK8s Add-ons

```bash
microk8s enable dns ingress storage
```

2. Clone and Deploy the Chart


```bash
git clone https://github.com/muhammadajnas/gitlab.git
cd gitlab

helm install gitlab ./
```
Port Forwarding

```bash
kubectl port-forward service/gitlab 8080:80
```


 http://localhost:8080


[GitLab CE Docker](https://hub.docker.com/r/gitlab/gitlab-ce/)

[Kubernetes](https://kubernetes.io/)

[Helm](https://helm.sh/)


