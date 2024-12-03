# Cosmocloud Deploy Helm Chart

This Helm chart is used to deploy a complete application stack consisting of a **Backend**, **Frontend**, and **Redis Database** on a Kubernetes cluster (AKS). The services are exposed using Kubernetes services, with a NodePort for frontend access and ClusterIP for backend and Redis services.

## Chart Overview

This Helm chart creates the following resources:
1. **Backend Deployment**: Deploys the backend service, which is exposed via a ClusterIP service (`backend-svc`).
2. **Frontend Deployment**: Deploys the frontend service, which is exposed via a NodePort service (`frontend-svc`).
3. **Redis Deployment**: Deploys the Redis database service, exposed via a ClusterIP service (`redis-svc`).

## Requirements

- Kubernetes cluster (e.g.,EKS, AKS)
- Helm installed and configured

## Chart Structure

- **Chart.yaml**: Contains metadata for the Helm chart.
- **templates/**: Contains Kubernetes manifests for deployments and services.
- **values.yaml**: Defines configurable values for the deployments and services.

## Installation

### Prerequisites
Ensure you have Helm installed and are connected to your Kubernetes cluster.

For deploying the application:

```helm install testapp ./cosmocloud-deploy --atomic --timeout 5m```

Once the app is up and running and testing you can delete teh resources by running following cmd:
```helm uninstall testapp```



