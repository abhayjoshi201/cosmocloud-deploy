# Cosmocloud Deploy

This Helm Chart deploys the following:
- Backend service
- Frontend service
- Redis database

## Components
### Backend
- Image: `shreybatra/sample-backend`
- Env Variable: `REDIS_URI=redis://redis-svc:6379`
- Exposed via `ClusterIP` service on port `8000`.

### Frontend
- Image: `shreybatra/sample-frontend`
- Env Variable: `BACKEND_URL=http://backend-svc:8000`
- Exposed via `NodePort` service on port `5173` (NodePort `31000`).

### Redis
- Image: `redis`
- Exposed via `ClusterIP` service on port `6379`.

## Installation
Run the following command:
```bash
helm install testapp cosmocloud-deploy --atomic --timeout 30s
