# SUMOT-deployment

This repository contains Kubernetes configuration files for deploying the SUMOT application using ArgoCD.

## Architecture
The deployment relies on a fully automated CI/CD pipeline:

1️⃣ CI (Continuous Integration):
- Any update to the SUMOT application repository triggers a Docker build.
- The built image is pushed to DockerHub with a versioned tag.

2️⃣ CD (Continuous Deployment):
- ArgoCD monitors this repository and automatically applies updates to the deployment configuration.
- Any update to the deployment/deployment.yml file triggers an automatic redeployment.

## Deployment
1️⃣ Update the Application Version
When a new version of the Docker image is available, update the deployment/deployment.yaml file to reference the new version:

yaml
Copier
Modifier
containers:
  - name: sumot
    image: marcderoo/sumot:vX.Y.Z  # Update with the new version
Then commit and push the changes:

bash
Copier
Modifier
git add deployment/deployment.yaml
git commit -m "Update to version vX.Y.Z"
git push origin main
ArgoCD will detect the change and automatically update the application.

2️⃣ Verify the Deployment
Once pushed, check the deployment status using:

bash
Copier
Modifier
kubectl get pods
kubectl get services
You can also monitor the deployment through the ArgoCD dashboard.

## Contributors

- 
