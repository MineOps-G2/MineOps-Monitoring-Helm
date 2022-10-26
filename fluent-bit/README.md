# Fluent-Bit

## Create RBAC resources for Fluent Bit

### Create ServiceAccount
```shell
kubectl create -f ./fluent-bit-service-account.yaml
```
### Create ClusterRole
```shell
kubectl create -f ./fluent-bit-role.yaml
```
### Create ClusterRoleBinding
```shell
kubectl create -f ./fluent-bit-role-binding.yaml
```

## Create Fluent Bit ConfigMap

### Create Configmap
```shell
kubectl create -f ./fluent-bit-configmap.yaml
```


## Fluent Bit Daemonset
```shell
kubectl create -f ./fluent-bit-daemonset.yaml
```