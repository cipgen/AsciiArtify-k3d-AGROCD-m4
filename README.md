<h3 align=center>AsciiArtify - k3d deployment</h3>


1. Installing k3d via Homebrew for managing Kubernetes clusters:
```console
brew install k3d
```
2. Creating a new Kubernetes cluster named "asciiartify":
```console
k3d cluster create asciiartify
```
4. Displaying information about the current state of the Kubernetes cluster:
```console
kubectl cluster-info
```
5. Deploying an application in the cluster using an image:
```console
kubectl create deployment python-hw-app --image=cipgen/python-hw-app:v1.0.1
```
6. Creating external access to the application through a LoadBalancer:
```console
kubectl expose deployment python-hw-app --type=LoadBalancer --port=8080
```
7. Viewing information about the service in the cluster:
```console
kubectl get services python-hw-app
```
8. Retrieving a list of all active pods in the cluster:
```console
kubectl get pods
```
9. Viewing logs of a specific pod (replace the identifier):
```console
kubectl logs python-hw-app-684f7f6846-7bbhf
```
10. Setting up port forwarding for accessing the service:
```console
kubectl port-forward service/python-hw-app 8080:8080
```

![Alt text](https://github.com/cipgen/AsciiArtify/blob/main/img/k3d.gif)
