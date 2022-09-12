# demo-argocd-config
Demo of the ARGO CD product in a local docker-desktop k8s installation.

Based on the youtube video https://www.youtube.com/watch?v=MeU5_k9ssrs 

## initial setup
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl -n argocd get secrets argocd-initial-admin-secret -o yaml
kubectl port-forward svc/argocd-server -n argocd 8080:443
kubectl -n argocd apply -f application.yaml
```

## CLI usage
```
brew install argocd
argocd login localhost:8080
(enter 'admin' as username and the password from the secrets)
argocd app get demo-argo-application
```
