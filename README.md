# demo-argocd-config

Based on the youtube video https://www.youtube.com/watch?v=MeU5_k9ssrs 

## initial setup
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl -n argocd get secrets argocd-initial-admin-secret -o yaml
kubectl port-forward svc/argocd-server -n argocd 8080:443
kubectl -n argocd apply -f application.yaml
```
