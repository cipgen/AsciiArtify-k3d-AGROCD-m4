<h3 align=center> <u> Demo - MVP + ArgoCD - k3d </u></H3>

**MVP:** To test the product with a focus group of users. At this stage, developers add additional features, fix bugs, and refine the product based on feedback received from users.

Forwarding port 443 of the remote argocd-server service in Kubernetes to port 8080 on my local computer using the kubectl port-forward command

```console
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

We add an application through the graphical interface, as shown in the pictures below.

pictures 
1-4

Get a list of services in the 'demo' namespace in Kubernetes using a short form of the kubectl get svc command.

```console
k get svc -n demo
```

We check the operation of the application. We forward port 8088 to 80 with the following command.

```console
kubectl port-forward -n demo svc/ambassador 8088:80
```

picture curl_test

We download any picture from the Internet for the test.

```console
wget -O /tmp/<name.png> <URL_picture.png>
```

Testing the application.

```console
curl -F 'image=@/tmp/<name.png>' localhost:8088/img/
```

**result**






