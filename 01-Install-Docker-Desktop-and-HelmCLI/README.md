## Requirements
* minikube
* docker
* kubectl

## Step 01: Run Minikube Locally
```t
minikube start
```


## Step 03: Run a simple application locally
```t
# Deploy k8s Resources to Docker Desktop k8s Cluster
kubectl apply -f kube-manifests/namespace.yaml && kubectl apply -f kube-manifests/

# Set the test namespace as default
kubectl config set-context --current --namespace=test

# List k8s Deployments
kubectl get deploy

# List k8s pods
kubectl get pods

# List k8s Services
kubectl get svc


#then access the application
open http://$(minikube ip):$(kubectl get service myapp1-nodeport-service -o=jsonpath='{.spec.ports[0].nodePort}')


# Uninstall k8s Resources from Docker Desktop k8s cluster
kubectl delete -f kube-manifests/

# Set the test namespace as default
kubectl config set-context --current --namespace=default

# List pods, svc, deploy
kubectl get pods
kubectl get svc
kubectl get deploy
```

## Step-07: Install Helm using Package Managers
- [Install Helm](https://helm.sh/docs/intro/install/)
```t
# install helm
sudo apt-get update
sudo apt-get install helm

# Verify Helm version
helm version

# Helm Environment variables
helm env
```