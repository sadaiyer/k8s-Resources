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
  
