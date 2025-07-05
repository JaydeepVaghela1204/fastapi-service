# FastAPI Service

## Overview
A simple Python FastAPI app with a `/status` endpoint.

## Setup

### Local Development
```bash
pip install -r requirements.txt
uvicorn main:app --host 0.0.0.0 --port 8000
```

Service runs on port 8000.

### Docker
```bash
docker build -t fastapi-service .
docker run -p 8000:8000 fastapi-service
```

### Kubernetes
Apply manifests in the `k8s/` directory:
```bash
kubectl apply -f k8s/
```

### Endpoints
- `GET /status` → Status check

### Example Response
```
{
  "status": "ok"
}
```

### CI/CD
Deployment is automated via GitHub Actions to AWS ECR/EKS. See `.github/workflows/deploy.yml`.

### Environment Variables
- Set via `k8s/configmap.yaml` and `k8s/secret.yaml`. 