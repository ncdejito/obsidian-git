[[Kubernetes (k8s)]]

[Getting started](https://microk8s.io/docs/getting-started)

Install on dev machine
```
sudo snap install microk8s --classic --channel=1.25
```

Deploy local images [source](https://microk8s.io/docs/registry-images)
```
docker build -t backend:local .
docker save backend > myimage.tar
microk8s ctr image import myimage.tar
```