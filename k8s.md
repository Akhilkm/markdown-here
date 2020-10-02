## Kubernetes Commands
```
Cluster Specific Commands
kubectl get nodes

NameSpace Specific Commands
kubectl get ns
kubectl create ns <<namespace name>>

Pod Specific Commnads
kubectl get pods
kubeclt describe pod <<pod name>> -n <<namespace>>
kubectl expose pod <<pod name> --port 80 --type=LoadBalancer --name=<<service name>
kubectl port-forward <<pod name>> 3000:80
kubectl attach <<pod name>> -i
kubectl exec <<pod>> -- command
kubectl label pods <<pod naem>> mylabel=newapp
kubectl run -i --tty busybox --image=busybox --restart=Never -- sh
kubectl logs <<pod name>>

Service Specific Commands
kubectl get services
kubectl describe service <<service name>>

General Commands
kubectl create -f <<path to file name>>

```

## Kubernetes Components
1. Control Plane Components 
```
kube-apiserver 
etcd
kube-scheduler 
kube-controller-manager 
    Node controller: Responsible for noticing and responding when nodes go down.
    Replication controller: Responsible for maintaining the correct number of pods for every replication controller object in the system.
    Endpoints controller: Populates the Endpoints object (that is, joins Services & Pods).
    Service Account & Token controllers: Create default accounts and API access tokens for new namespaces.
cloud-controller-manager 
    Node controller: For checking the cloud provider to determine if a node has been deleted in the cloud after it stops responding
    Route controller: For setting up routes in the underlying cloud infrastructure
    Service controller: For creating, updating and deleting cloud provider load balancers
```
2. Node Components 
```
kubelet
kube-proxy 
Container runtime 
```
3. Addons
```
DNS
Web UI (Dashboard) 
Container Resource Monitoring 
Cluster-level Logging 
```

## Kubernete Documentations
```
Port: exposes the Kubernetes service on the specified port within the cluster. Other pods within the cluster can communicate with this server on the specified port.

TargetPort: is the port on which the service will send requests to, that your pod will be listening on. Your application in the container will need to be listening on this port also.

NodePort: exposes a service externally to the cluster by means of the target nodes IP address and the NodePort. NodePort is the default setting if the port field is not specified.
```
