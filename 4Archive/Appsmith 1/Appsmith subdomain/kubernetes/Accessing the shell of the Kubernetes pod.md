#### get the pods
```shell
kubectl get pods -n appsmith
```
we copy the ID of the appsmith pod
#### access the pods shell
```shell
kubectl exec -it <pod name> -n appsmith sh
```