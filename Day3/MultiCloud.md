# Connecting Kubernetes Clusters Across Cloud Providers 
* Thomas Graf @tgraf - Isovalent 
* Cilium Project 
* BPF - http://man7.org/linux/man-pages/man2/bpf.2.html
  * sandboxed vm in the linux kernel
  * used for tracin, virtual networking  
  * Google, RHEL, Netflix, Facebook are a big user
* Setup two clusters - GKE and EKS with Encryption 
* Tools 
  * Kubernets 
  * Infrastructure APIs - VPC with routing. IPSec VPN Gateway with IKEv1 support 
  * Cilium - https://github.com/cilium/cilium
    * based on BPF technology.  A better iptables (?) 
    * CNI plugin 
    * Replaces kube-proxy.  
    * Network Security - identity-based, DNS aware, API aware 
    * Envoy/Istio Intgration 
      * Sidecar and Transparent SSL visibiliyt (kTLS)
    * API aware security
* kubectl get svc backend  
* kubectl get endpoints backend 
  * Liviness Probes 
* https://docs.cilium.io 
* Only syncs services at this point
  * Does not sync secrets/ConfigMaps 
* 
## Global Services 
* annotation to mark a service as global 
* io.cilium/global-service: "true"

## Design Principles
* Simple to use 
* Simple to troubleshoot
* Resilient - preserve and respect AZs and Fault Domains 
  * Failures in one cluster should not impact other clusters
* Secured with Encryption. mTLS compatibility 
* Efficient with near native networking speed. 
  * Direct pod to pod wihtout intermediate terminations

## Annotations
* io.cilium/global-service
* io.cilium/shared-service 
* io.cilium/service-affinity - coming soon

## Control Plane
* Deployed to a namespace
* DaemonSet on all nodes
* Operator 
* Has its own etcd in each cluster
* Service exposed by your VPC (not public)

## VPC Setup
* CIDR blocks must be unique. 
* Establish a VPN gateway/tunnel (2 for production )
* Setup routes 

## Kubernetes Setup
* Setup your K8S clusters 
* Deploy Cilium 
* Extract etcd secrets from one cluster and add to other cluster 
* Introduces ideas around having clusters for stateless applications and stateful applications 

## Istio Integration 
* Istio / Kuberenetes - Control Planes
* Envoy / Cilum - Dataplane 
* Istio services can be supported with the same 
  
## Demo
* EKS and GKE.
* Clusters are indendepent 
* K scale deployment rebel-base --replicas=0
* Cilium Network Policy - you can define global policies or cluster based policies 