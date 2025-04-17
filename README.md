# SUMOT-deployment

This repository contains Kubernetes configuration files for deploying the SUMOT application using ArgoCD.
The main repository of the project is located to : https://github.com/marcderoo/SUMOT.git

## Architecture
The deployment relies on a fully automated CI/CD pipeline:

1️⃣ CI (Continuous Integration):
- Any update to the SUMOT application repository triggers a Docker build.
- The built image is pushed to DockerHub with a versioned tag.

2️⃣ CD (Continuous Deployment):
- ArgoCD monitors this repository and automatically applies updates to the deployment configuration.
- Any update to the deployment/deployment.yml file triggers an automatic redeployment.

## Deployment
Once pushed, check the deployment status using:

```bash
kubectl get pods
kubectl get services
```

You can also monitor the deployment through the ArgoCD dashboard.

## Contributors

- Maxime Chappuis

- Arnaud Cournil

- Marc Deroo

- Meryem El Aissaoui

- Laurent Vong
