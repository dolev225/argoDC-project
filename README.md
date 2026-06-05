# Argocd Kubernetes Gitops Tutorial

This repo contains all the code needed to follow along with our **[YouTube Tutorial](https://youtu.be/yj4O0wwkMQI)** or **[Written Article](https://rslim087a.github.io/rayanslim/lesson.html?course=argocd-gitops-course&lesson=introduction)**.

## Prerequisites

To follow along with this tutorial, you'll need:

- kubectl installed and configured ([https://youtu.be/IBkU4dghY0Y](https://youtu.be/IBkU4dghY0Y))
- Helm installed: [https://rslim087a.github.io/rayanslim/lesson.html?course=prometheus-grafana-monitoring-course&lesson=helm-installation](https://rslim087a.github.io/rayanslim/lesson.html?course=prometheus-grafana-monitoring-course&lesson=helm-installation)
- A GitHub account: ([https://github.com/](https://github.com/))

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
