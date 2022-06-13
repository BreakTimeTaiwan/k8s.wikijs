### login azure service
```shell
az login 
az account set --subscription 1d91e718-bad6-4cd8-b843-161a96f310b1
az aks get-credentials --resource-group mark-terraform-test-rg --name mark-k8s-terraform-test
```
### Create namespace and pvc
```shell
kubectl apply -f create-namespace.yaml 
kubectl apply -f wiki-storage-class.yaml 
kubectl apply -f wiki-pvc.yaml 
```

### Create postegres service
```shell
kubectl apply -f postgres-secret.yaml 
kubectl apply -f postgres-config.yaml 
kubectl apply -f postgres-deployment.yaml 
kubectl apply -f postgres-service.yaml 
```
### Create adminer service
```shell
kubectl apply -f adminer-config.yaml 
kubectl apply -f adminer-deployment.yaml 
kubectl apply -f adminer-service.yaml 
kubectl apply -f adminer-ingress.yaml 
```

### Create wiki service
```shell
kubectl apply -f wiki-secret.yaml 
kubectl apply -f wiki-config.yaml 
kubectl apply -f wiki-deployment.yaml 
kubectl apply -f wiki-service.yaml
kubectl apply -f wiki-ingress.yaml 
```