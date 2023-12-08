<h3 align=center> <u> Demo - instrall ArgoCD - k3d </u></H3>

Install k3d, a tool for running lightweight Kubernetes (k3s) clusters in Docker, via Homebrew.
```console
brew install k3d
```
Create a k3d cluster named 'demo' with three worker nodes (agents).
```console
k3d cluster create demo --agents 3
```
Display information about the Kubernetes cluster, including the master node and service addresses.
```console
kubectl cluster-info
```
List all nodes in the Kubernetes cluster, showing their statuses.
```console
kubectl get nodes
```
Create a new namespace 'argocd' in the Kubernetes cluster.
```console
kubectl create namespace argocd
```
Install Argo CD in the 'argocd' namespace using the manifest from the provided URL.
```console
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
Forward traffic from local port 8080 to port 443 of the 'argocd-server' pod.
```console
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
Retrieve and decode the Argo CD admin password.
```console
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
Install the Argo CD CLI via Homebrew.
```console
brew install argocd
```
Log into Argo CD via CLI, connecting to the server at 'localhost:8080'.
```console
argocd login localhost:8080
```
Change the account password in Argo CD via CLI.
```console
argocd account update-password
```
![PoC](https://github.com/cipgen/AsciiArtify/blob/main/img/poc.gif)
