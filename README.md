# argocd-wordpress-rds

GitOps is a way of implementing Continuous Deployment for cloud applications. It allows developers to deploy faster and more often by using tools that developers are already familiar with such as Git and other CD tools

ArgoCD completes the most crucial step of GitOps by ensuring that the repository and production environment states are always in sync. It reports & visualizes any deviation as well as provides mechanisms to automatically or manually sync the live state to the desired target state.

Steps Implemented

1. Created new namespace for ArgoCD and installed ArgoCD on Kubernetes using below commands

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
2. Connected to git repository using SSH key
3. Created two new repos on github(one forlocal mysql and another to connect to rds)
4. Created two applications on Argocd UI
5. Syncronized with latest code changes and deployed application to wordpress namespace
6. Whenever there is a new commit to both the repos, ArgoCD will detect changes and deploy changes to Kubernetes.
7. With ArgoCD, single source of truth(Git) can be achieved to know the status of Kubernetes Cluster deployments.
