# Kubernetes Scalability: A multi-dimensional analysis 
* Maciek Rozacki                                                                 
* Many people in the room with 1000+ nodes 
* Why are clusters << 5000 nodes running into scale issues 
* Scalabilty is not a single number 
  * #Nodes is a proxy for 'scale'
  * 'Support' up to 5000 nodes 
* Scalability is a subspace of configurations 
  * think of it as a cube - higher dimensional 
* dimensions that describe your cluster are probably not independent 
* dimensions probably do not scale linearly 
  * don't push too many dimensions at once ! 
* There are hard limits. Primary due to limits etcd size 
  * Crude estimate is a limit of about ~ 300,000 objects in etcd
* k8s control plane scaling is in general not specific to any cloud provider
* Reach out to sig-scalability 
* limits
  * #Nodes vs #Pods/node
    * 5000 nodes and api server starts to get overloaded
    * 110 pods/nodes and kubelet starts to get overloaded 
      * assume <= 2 containers per pod 
    * ~150K pods in total in your cluster will start adding loads to api server and kubelet 
  * Services vs Backends/Service - not hard limits
    * 250 Backends/service - endpoints traffic becomes larger after 250 (quaratic)
    * 10k services - iptables startes to degrade
    * Example of Scaling being Quadratic 
      * 7500 services of a size 5 backends
      * 600 services of a size 30 backends
      * 75 services of a size 250 backends
  * Services per Namespace
    * 5k services per namespace 