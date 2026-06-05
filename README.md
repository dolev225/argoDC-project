
## Install ArgoCD on your Cluster
```
kubectl create namespace argocd
helm repo add argocd https://argoproj.github.io/argo-helm 
helm repo update
helm upgrade --install -n argocd argocd argocd/argo-cd

```

## Access ArgoCD UI

```
kubectl -n argocd port-forward svc/argocd-server 8080:80
```

## Retrieve Credentials

```
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d && echo
```



Learn every tool that matters: [https://rslim087a.github.io/rayanslim](https://rslim087a.github.io/rayanslim)
