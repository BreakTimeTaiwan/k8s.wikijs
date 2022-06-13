### login azure service
```shell
az login 
az account set --subscription 1d91e718-bad6-4cd8-b843-161a96f310b1
az aks get-credentials --resource-group mark-terraform-test-rg --name mark-k8s-terraform-test
```
### Create namespace and pvc
```shell
kubectl create namespace wiki
kubectl apply -f wiki-storage-class.yaml -n=wiki
kubectl apply -f wiki-pvc.yaml -n=wiki
```

### Create postegres service
```shell
kubectl apply -f postgres-secret.yaml -n=wiki
kubectl apply -f postgres-config.yaml -n=wiki
kubectl apply -f postgres-deployment.yaml -n=wiki
kubectl apply -f postgres-service.yaml -n=wiki
```
### Create adminer service
```shell
kubectl apply -f adminer-config.yaml -n=wiki
kubectl apply -f adminer-deployment.yaml -n=wiki
kubectl apply -f adminer-service.yaml -n=wiki
kubectl apply -f adminer-ingress.yaml -n=wiki
```

### Create wiki service
```shell
kubectl apply -f wiki-secret.yaml -n=wiki
kubectl apply -f wiki-config.yaml -n=wiki
kubectl apply -f wiki-deployment.yaml -n=wiki
kubectl apply -f wiki-service.yaml -n=wiki
kubectl apply -f wiki-ingress.yaml -n=wiki
```