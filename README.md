# Kubernetes

This repo consists of kubernetes YAML files, which are deployed in a kubernetes cluster using argocd.

# ArgoCD

ArgoCD is a declarative, GitOps continuous delivery tool for Kubernetes.
Argo CD follows the GitOps pattern of using Git repositories as the source of truth for defining the desired application state.


# Installing ArgoCD

- kubectl create namespace argocd
- kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


Retrieving the ArgoCD password
- kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

Connect to the ArgoCD UI
- kubectl -n argocd port-forward svc/argocd-server 8081:8080
- http://localhost:8081
