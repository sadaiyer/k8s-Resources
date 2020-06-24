### Section 6 - Cluster Maintenance 
### 1. OS Upgrade
``` kubectl drain node01  -- evicts all the pods running on the node and not schedule any new pods  -- used before the upgrading OS
kubectl conrdon node01  -- no new pods are scheduled but the existing pods continue to run  -- getting ready for upgrade
kubectl uncordon node01 -- starts scheduling new pods -- after upgrade of the OS
```
### 1. kubernetes software versions
* You can find all the releases in the releases page of the Kubernetes Github repository.
* Download the kubernetes.tar.gz file and extract it to find executables for all the kubernetes components. The downloaded package when extracted has all the control plane components in it.
#### ControlPlane Components
* Kube - API Server
* Controller - Manager
* Kube-scheduler
* kubelet
* kube-proxy
-- The above have the same version number
* ETCD 
* CoreDNS 
-- These two different versios
### 1. Cluster Upgrade process
### 1. Reference

https://blog.risingstack.com/the-history-of-kubernetes/
