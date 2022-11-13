

Documentation:
https://helm.sh/docs/topics/charts/

1. Installing helm 
```
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh
```
2. Add Helm repository  

```
helm repo add stable https://charts.helm.sh/stable
helm repo add bitnami https://charts.bitnami.com/bitnami
helm search repo nginx

```
3. Install helm chart
```
helm install bitnami/nginx
```

5. Verify the installation 
```
kubectl get all


```
helm list

```

helm install <chart>
  
Upgrade using helm

  helm upgrade <chart>
