# CKA Study

# Section 3 - Scheduling

## 1.  Manual Scheduling
## 2.  Labels and Selectors
## 3.  Taints and tolerations
## 4.  Node Selector: 
	* works with labels. 
	* Nodes need to label first, then use nodeSelector in the pod definition file. 
	```
	   nodeSelector: 
	     size: Large
	```
    -   Limitations of the Node Selector Need to place a pod on the node size. How to achive this. Need to use NodeAffinity
        -   Large or medium
        -   not Small
## 5. Node Affinity
## 6. Taints and Tolerations and Affinity
## 7. DaemonSets
	* Similar to replica set
	* DaemonSets run one copy of pod on each node all the time. 
 	* Use Cases
		* Monitoring Solutions
		* Log viewer Solutions
		* Kube Proxy can be deployed as DaemonSet
		* Networking Solutions - wavenet
	How to create a DaemonSet?
		kubectle create daemonset 
		kubectl describe daemeonset
		
	How does it work?
		* How does daemonset places one pod on each node
		Ans: 
		     * uses kube scheduler
		     * uses node affinity rules
## 8. Static Pods
	* kubelet reads the <pod definition file>.yaml in /etc/kubernetes/manifest directory
	* This directory can be any directory passed as a parameter, pod-manifest-path=<directory>  while running kubelet service 
	* or configpath=kubeconfig.yaml which has staticpodpath=<directory Name>
	* static pods are not dependent on control plane
### How does kubelet creates a pods
	* kubelet takes input for creating pods from different sources
		* static pods creation like the above
		* http api end point. Kube api server povides input to the kubelet
### Use cases
	* Static pods are used to deploy kubernetes control plane components itself on multiple nodes as pods.
	* kubeadm tool setsup the kubernetes cluser by using the static pods.
	* start by installing a kubelet on each master node, then placing the pod definition files that uses the docker images of various   control plane components. Then kubelet takes care of deploying control plane components on each master nodes
	* Other way of setting up kubernetes cluster is downloading images and configuring various services, then manually taking care of them when they creash etc. 
	* Advantage of deploying kubernetes control plane as static pods is kubelet takes care of them if they fail by restarting them. 
### difference between static pods and Daemonsets

## 9. Multiple schedulers
```* kubernetes cluser can have multiple schedulers
* you can have a pod or deployment scheduled by a specific scheduler
```
#### How to deploy a additional scheduler as service
```1) download the binary from <>
2) run it as service
```
#### How to deploy an additional scheduler using kubeadm tool
```1) kubeadm tool deploy the scheduler as pod
2) you can find the scheduler definition file under manifest directory
to view the scheduler: kubectl get pods --namespace=kube-system
```
#### how to specify a pod to use a non-default scheduler
``` * specify  schedulerName: <custom scheduler Name> in pod specification
