# @TODO we should explain the process of setting up the single node cluster with talos linux and the day0 operations with argo






# Day 0 

- manually install ArgoCD from the helm chart at day0/argocd
- apply the bootstrap/day0-initializer.yaml; this Application points to the day0-appset where all the other Applications are templated

Get initial admin secret for ArgoCD GUI:
```shell
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath={".data.password"} | base64 -d
```


## Headlamp

headlamp.10.254.102.21.nip.io

create token: 

```shell
kubectl create token headlamp
```
