# Build image
docker build -t localhost/golang-app:v1 .

# Test the image locally
docker run -p 8080:8080 localhost/golang-app:v1

# Push to registry
docker push localhost/golang-app:v1

# Apply deployment
kubectl apply -f deployment.yaml

# Apply service
kubectl apply -f service.yaml

# Check pods
kubectl get pods

# Check service
kubectl get svc

# Check deployment
kubectl get deployment

