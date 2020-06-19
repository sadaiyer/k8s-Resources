# CKA Study

# Section 3 - Scheduling

1.  Manual Scheduling
2.  Labels and Selectors
3.  Taints and tolerations
4.  Node Selector: 
	* works with labels. 
	* Nodes need to label first, then use nodeselector in the pod definition file. 
		
		```nodeSelector: 
			 `size: Large
		```
    -   Limitations of the Node Selector Need to place a pod on the node size. How to achive this. Need to use NodeAffinity
        -   Large or medium
        -   not Small


