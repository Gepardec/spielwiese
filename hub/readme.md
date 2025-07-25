# @TODO we should explain the process of setting up the single node cluster with talos linux and the day0 operations with argo


Missing: 

- Installation Process of Talos Linux + Cluster
- Commit the config.yaml for the single node cluster
- Ingress Setup



KubeConfig for the cluster is in Keeper, can be shared by Marko, Constantin and Tobias

# Day 0 

- manually install ArgoCD from the helm chart at day0/argocd
- apply the bootstrap/day0-initializer.yaml; this Application points to the day0-appset where all the other Applications are templated


## ArgoCD

[argocd.10.254.102.21.nip.io](argocd.10.254.102.21.nip.io)

Get initial admin secret for ArgoCD GUI:
```shell
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath={".data.password"} | base64 -d
```


## Headlamp

[headlamp.10.254.102.21.nip.io](headlamp.10.254.102.21.nip.io)

create token: 

```shell
kubectl create token headlamp
```

## Crossplane 

Provider can be found in templates/provider, this is the initial connection configuration

Provider Config in templates/provider-config defines the CRDs for said provider

