<h3 align=center>AsciiArtify - k3d deployment</h3>


1. Installing k3d via Homebrew for managing Kubernetes clusters:
   `brew install k3d`

2. Creating a new Kubernetes cluster named "asciiartify":
   `k3d cluster create asciiartify`

3. Displaying information about the current state of the Kubernetes cluster:
   `kubectl cluster-info`

4. Deploying an application in the cluster using an image:
   `kubectl create deployment python-hw-app --image=cipgen/python-hw-app:v1.0.1`

5. Creating external access to the application through a LoadBalancer:
   `kubectl expose deployment python-hw-app --type=LoadBalancer --port=8080`

6. Viewing information about the service in the cluster:
   `kubectl get services python-hw-app`

7. Retrieving a list of all active pods in the cluster:
   `kubectl get pods`

8. Viewing logs of a specific pod (replace the identifier):
   `kubectl logs python-hw-app-684f7f6846-7bbhf`

9. Setting up port forwarding for accessing the service:
```console
   `kubectl port-forward service/python-hw-app 8080:8080`
```
