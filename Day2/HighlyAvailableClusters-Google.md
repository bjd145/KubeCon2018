# Creating Highly Available Clusters 
* Karan Goel (karangoel) and Meaghan Kjelland (@meaghnk)
    * Developes on GKE On-prem team 
* http://github.com/bradfitz/homelab 
* Multi-master is not enough 
* What can fail
    * Apps
    * Cooling
    * ISP
    * Network Partitions 
    * Hypervisor 
    * Virtual / Physical machines
    * Power
    * Storage 
* GKE Failure Domains - Zones and Regions 

## Applications
* Schedule pods across zones is not a part of K8S
* Add labels to Nodes
* Add podAntiAffinity 
* Cloud Providers manage this for you 
* Node Upgrades 
    * PodDisruptionBdudget + kubectl drain 
    * Pod Eviction API rejects calls 

## Control Plane 
* Pods will still run if the control plane goes away.  Just new woarkloads will not be scheduled 
* Run master nodes across zones 
* Easy for API server 
* schedule and controller manager are harder since they have to read/write data.
    * locking mechanism 
* Configure leader election 
    * --leader-elect = true 
* Options to explore - managed instance groups, hosted solutions, build your own monitoring server, k8s itself 
    * self-hosted kubernetes ???
    * management cluster - two clusters. Cluster A's worker nodes are the control plane for cluster B
    * cluster-api - sig-clusterlifecycle 

## Data Plane 
* etcd is special because its a database 
* need an elctive leader for quorum 
* need N/2 + 1 master nodes 
* HA upgrade 
* Periodic backups of etcd
* alerting when backups are too stale
* automatically test restore 
* coreos.com/etcd/docs/latest/op-guide/recovery.html 
* Ark from Heptio 
    * Does require the API server 
* etcd Operator 
* etcdctl snapshot + cron
