[[Distributed Systems]]

## References
From awesome k8s resources
- [Illustrated guide to kubernetes](https://www.cncf.io/phippy/the-childrens-illustrated-guide-to-kubernetes/ ) - Terminologies as illustrations!! 
- [A beginners guide to kubernetes](https://medium.com/containermind/a-beginners-guide-to-kubernetes-7e8ca56420b6)
- [Kubernetes - Terraform](https://faun.pub/google-kubernetes-engine-explain-like-im-five-1890e550c099)
- [Kubernetes - Prometheus](https://faun.pub/production-grade-kubernetes-monitoring-using-prometheus-78144b835b60)
- Official k8s online tutorial
- [k0s](https://github.com/k0sproject/k0s) - zero friction kubernetes, an all-inclusive Kubernetes distribution, which is configured with all of the features needed to build a Kubernetes cluster and packaged as a single binary for ease of use.

Install minikube [source](https://minikube.sigs.k8s.io/docs/start/)
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

Install kubectl
```
## download binary
curl -LO https://dl.k8s.io/release/v1.25.0/bin/linux/amd64/kubectl
## validate checksum
curl -LO "https://dl.k8s.io/release/v1.25.0/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
## install
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```


