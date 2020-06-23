# Section 4 - Logging and Monitoring
### 1. Monitoring
#### * Monitoring resource consumption
* Monitoring node level metrics
  * number of nodes in the cluster
  * How many of them are healthy
  * Node level perforamnce metrics
    * CPU
    * Memory
    * Disk utilization
  * POD level Metrics
    * Number of PODS
    * Performance metrics of each pod like CPU, Memory etc
#### * Metrics solutions
K8s doesn't come with builtin monitoring solution. we need to choose and install one of the following solution or develop one.
  1. Metrics server
  1. Prometheus
  1. Elastic Stack
  1. Data Dog
  1. dynatrace
##### Metrics Server
* Heapster - original solution, depracated now
* In memory only, doesn't store any inforamtion. Hence no history avaiable
###### Kubelet - cAdvisor
Is part of kubelet, responsible for retreiving metrics from pods and exposing them / forwarding them through the kubelets API to the metrics server
### Metrics server Installation
#### - Minikube - type k8s deployment
if the cluster is installed through the minikube, then metrics server is addon plugin
``` minikube addons enable metrics-server ```
#### - for all other type deployment
``` git clone https //github.com/kubernetes-incubator/metrics-server ```
* Then deploying all the components through the kubectl command
``` kubectl create -f deploy/1.8+/. ```
* deploys set of pods, services and roles 
### Viewing Metrics
``` kubectl top nodes
kubectl top pod
```

### 2. Various logging mechanisms in K8s
#### Application Logs
* Pod level logging is by default enabled
* to view the pod level logging use ``` kubectl logs -f <POD Name> ```
* these logs are specific to containers running inside the pod
* 

## References
[Metrics Server Installation from Medium](https://medium.com/@cagri.ersen/kubernetes-metrics-server-installation-d93380de008)
[Github resource](https://github.com/kubernetes-sigs/metrics-server)


