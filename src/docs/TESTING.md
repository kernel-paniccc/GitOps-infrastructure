---

## Testing with Docker

If the application is running in Docker:

```bash
# Build the image
docker build -t metric2deploy ./src

# Run the container
docker run -d -p 80:80 --name metric2deploy metric2deploy

# Test endpoints
curl http://localhost/health
curl http://localhost/time

# Stop the container
docker stop metric2deploy
docker rm metric2deploy
```

---

## Testing in k3s Cluster

After deploying to k3s:

```bash
# Get the service IP
kubectl get services

# Test via NodePort or Ingress
curl http://<cluster-ip>/health
curl http://<cluster-ip>/time
```

---
