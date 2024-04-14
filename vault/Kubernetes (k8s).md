[[System Design]]

## Definitions
- ClusterIP (default) - Exposes the Service on an internal IP in the cluster. This type makes the Service only reachable from within the cluster.
- NodePort - Exposes the Service on the same port of each selected Node in the cluster using NAT. Makes a Service accessible from outside the cluster using NodeIP:NodePort. Superset of ClusterIP.
- LoadBalancer - Creates an external load balancer in the current cloud (if supported) and assigns a fixed, external IP to the Service. Superset of NodePort.
- ExternalName - Maps the Service to the contents of the externalName field (e.g. foo.bar.example.com), by returning a CNAME record with its value. No proxying of any kind is set up. This type requires v1.7 or higher of kube-dns, or CoreDNS version 0.0.8 or higher.

## Routines

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

## Basics
https://kubernetes.io/docs/tutorials/kubernetes-basics/

### Create a Kubernetes cluster
```
minikube version
minikube start
kubectl version
kubectl cluster info
kubectl get nodes
```

### Deploy an app
```
kubectl version
kubectl get nodes

# deploy
kubectl create deployment kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1
kubernetes get deployments

# create proxy that forwards communications into cluster-wide private network
echo -e "\n\n\n\e[92mStarting Proxy. After starting it will not output a response. Please click the first Terminal Tab \n";
kubectl proxy

curl http://localhost:8001/version

# get pod name, store as env variable
export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
echo Name of the Pod: $POD_NAME

curl http://localhost:8001/api/v1/namespaces/default/pods/$POD_NAME/
```

### Explore your app
```
kubectl get pods
kubectl describe pods

echo -e "\n\n\n\e[92mStarting Proxy. After starting it will not output a response. Please click the first Terminal Tab\n";
kubectl proxy

export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
echo Name of the Pod: $POD_NAME

curl http://localhost:8001/api/v1/namespaces/default/pods/$POD_NAME/proxy

kubectl logs $POD_NAME

# execute commands directly on the container
kubectl exec $POD_NAME -- env

# start a bash session in pod's container
kubectl exec -ti $POD_NAME -- bash

# check application is running
curl localhost:8080
```

### Expose your app publicly
```
kubectl get services
kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080
kubectl get services # check it has kubernetes-bootcamp

kubernetes describe services/kubernetes-bootcamp
export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')
echo NODE_PORT=$NODE_PORT
curl $(minikube ip):$NODE_PORT

# query list of pods based on label (-l)
kubectl describe deployment
kubectl get pods -l app=kubernetes-bootcamp
kubectl get services -l app=kubernetes-bootcamp
export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
echo Name of the Pod: $POD_NAME
kubectl label pods $POD_NAME version=v1
kubectl describe pods $POD_NAME
kubectl get pods -l version=v1

kubectl delete service -l app=kubernetes-bootcamp
kubectl get services
curl $(minikube ip):$NODE_PORT # confirm that route is not exposed anymore
# curl inside the pod
kubectl exec -ti $POD_NAME -- curl localhost:8080
```

### Scale up your app
```
kubectl get rs # see the replicaset
kubectl scale deployments/kubernetes-bootcamp --replicas=4
kubectl get pods -o wide
kubectl describe deployments/kubernetes-bootcamp

kubectl describe services/kubernetes-bootcamp
export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')
echo NODE_PORT=$NODE_PORT
curl $(minikube ip):$NODE_PORT # execute multiple times to hit different pods

kubectl scale deployments/kubernetes-bootcamp --replicas=2
```

### Update your app
```
kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=jocatalin/kubernetes-bootcamp:v2

kubectl describe services/kubernetes-bootcamp
export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')
echo NODE_PORT=$NODE_PORT
curl $(minikube ip):$NODE_PORT

kubectl rollout status deployments/kubernetes-bootcamp

kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=gcr.io/google-samples/kubernetes-bootcamp:v10

kubectl rollout undo deployments/kubernetes-bootcamp
```


## References
From awesome k8s resources
- [Illustrated guide to kubernetes](https://www.cncf.io/phippy/the-childrens-illustrated-guide-to-kubernetes/ ) - Terminologies as illustrations!! 
- [A beginners guide to kubernetes](https://medium.com/containermind/a-beginners-guide-to-kubernetes-7e8ca56420b6)
- [Kubernetes - Terraform](https://faun.pub/google-kubernetes-engine-explain-like-im-five-1890e550c099)
- [Kubernetes - Prometheus](https://faun.pub/production-grade-kubernetes-monitoring-using-prometheus-78144b835b60)
- [Kubernetes - Grafana](https://devopscube.com/setup-grafana-kubernetes/)
- Official k8s online tutorial
- [k0s](https://github.com/k0sproject/k0s) - zero friction kubernetes, an all-inclusive Kubernetes distribution, which is configured with all of the features needed to build a Kubernetes cluster and packaged as a single binary for ease of use.
- Mount kubernetes pods with hardware [github](https://github.com/kubernetes/kubernetes/issues/7890#issuecomment-766088805)
- Enter a pod [blog](https://www.ibm.com/docs/SSCKRH_1.1.0/platform/t_accessing_docker_container_kubernetes.html)
- [Kubernetes learning path](https://github.com/techiescamp/kubernetes-learning-path)

## Tools
kubeshark - kubeshark api traffic inside k8s