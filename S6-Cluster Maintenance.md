### Section 6 - Cluster Maintenance 
### 1. OS Upgrade
``` kubectl drain node01  -- evicts all the pods running on the node and not schedule any new pods  -- used before the upgrading OS
kubectl conrdon node01  -- no new pods are scheduled but the existing pods continue to run  -- getting ready for upgrade
kubectl uncordon node01 -- starts scheduling new pods -- after upgrade of the OS
```
### 2. kubernetes software versions
* You can find all the releases in the releases page of the Kubernetes Github repository.
* Download the kubernetes.tar.gz file and extract it to find executables for all the kubernetes components. The downloaded package when extracted has all the control plane components in it.
#### ControlPlane Components
-- Following are also called core components of the cluster
* Kube - API Server
* Controller - Manager
* Kube-scheduler
* kubelet
* kube-proxy
-- The above have the same version number
* ETCD 
* CoreDNS 
-- These two different versios
### 3. Cluster Upgrade process
* Do core components have to be the same version? \
Ans. No, No they cane be one oversion below than API version \
* Kube - API Server  - X version \
-- X-1 version \
* Controller - Manager \ 
* Kube-scheduler  \
-- X-2 version \
-- X+1 > X-1
* kubelet 

* kube-proxy


### 4. Reference

[History of Kubernetes](https://blog.risingstack.com/the-history-of-kubernetes/) \
[Releases Page](https://github.com/kubernetes/kubernetes/releases/) \
https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md \
https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api_changes.md \
https://kubernetes.io/docs/concepts/overview/kubernetes-api/ \



