# Kubernetes | k8s

- Helps in scaling application
- It's a system for running many diff containers on multiple diff machines
- Usage : when you need to run many diff conatiners with diff images
- VMS are called nodes
  - nodes are individual vms that contain containers
  - nodes are managed by master
- kube-proxy is connection to outside workd
- nodes
  - pod
    - runs containers that need to be in a same network
    - nginx container
- label in pod | selector in service pairs -> used to setup forwarding/routing.
  - these are like key value pairs used for connection.
- master keeps no of containers running in a node in check
  - tells nodes to create certain copies of some container when required
- use declaritive approach not imperitive
  - declaritive
    - update config file
    - upload config file
    - all done automatically
- deployments
  - can run multiple pods
  - overcomes limitations of pods
  - best for dev and prod purposes
- services
  - help us to connect to different pods inside a deployment

## Phases

- dev : minikube
  - > minikube start
  - > minikube status
  - > minikube stop
  - > kubectl cluster-info
  - kubectl : for interacting with it
- prod : managed solutions like in EKS(amazon), GKE(gcloud)

## yml conf-files

- these files create an object.
  - StatefulSet
  - ReplicaController
  - Pod -> runs one or more closely related containers
  - Services -> helps setup networking
    - ClusterIP
    - NodePort
    - LoadBalancer
    - Ingress

- kind : object type -> every object has specific container
- apiVersion : v1
  - componentStatus
  - configMap
  - Endpoints
  - Event
  - Namespace
  - Pod

## kubectl

- run these to run object instances

```
> kubectl apply -f client-pod.yaml
> kubectl apply -f client-node-port.yaml
```

- find status of various object instances created

```
> kubectl get pods
> kubectl get pods -o wide
> kubectl get services
```

- deleting various object instances

```
> kubectl delete pod client-pod
> kubectl delete service client-node-port
<!-- this is an imperitive update -->
> kubectl delete -f config_name.yaml
```

- describe/investigate the object

```
> kubectl describe <object_type> <object_name>
> kubectl describe pod client-pod
``` 

- start deployment

```
> kubectl apply -f config_file.yaml
```

## minikube

- access our app

```
> minikube ip
Go to ip:/nodeport
```

- access dashboard (web interface)

```
> minikube dashboard
```