# devops-practical

A Flask web application with a complete CI/CD pipeline: automated testing, Docker, Kubernetes and continuous deployment.

**Live application:** https://devops-practical.vercel.app

| Resource | Link |
|---|---|
| Live application | https://devops-practical.vercel.app |
| Docker Hub image | https://hub.docker.com/r/dilshan24142/flask-app |
| Pipeline runs | https://github.com/dilshan24142/devops-practical/actions |

## Pipeline

1. **CI** (`.github/workflows/ci.yml`): installs dependencies and runs `pytest` on every push to `main`.
2. **Docker and Kubernetes** (`.github/workflows/docker-k8s.yml`): builds and runs the Docker image, pushes it to Docker Hub, deploys the `k8s/` manifests to a Kubernetes cluster with 2 replicas, and runs a chaos test (deletes a pod and verifies Kubernetes replaces it).
3. **CD**: every push to `main` is automatically deployed to the live URL.

## Run locally

```
pip install -r requirements.txt
python app.py
```

Then open http://localhost:5000. Run the tests with `pytest`.
