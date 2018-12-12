# Lyft Case Study - Hybrid Environment with k8s and Envoy 
* @litacho 
* @junr03
* Had issues with scaling on AWS - 20 minutes to add
    * Big fight days with very little historical data. Unprepared for growth 
* Like separation of concerns
* Benefits of Immutable Infrastructure 
* Hybrid Service Discovery 
  * Every 30 seconds side cars register services with a Service Discovery API (outside of k8s)
  * Rolling out k8s in parallel 
  * Envoy xDS Control Plane outside of k8s pushes configuration to k8s sidecars and legacy sidecars 
  * No ingress controllers in their environment. Each pod gets an IP address on their VPC
* Rollbacks are an important goal 

# Take Aways
* Eventual Consistency - friend or foe 
* Unified Observabilty 
* 

# Observation 
* Startups encounter the same problems with legacy as most enterprise 
* Everything is automated
* Commited to continually innovate and improve, even if its expensive 
* Iteratations 
* Willingness to experiement and learn
* Security still spooks developers in startups and fights between security / appdev 
* Compliance is not a big issue but observability is 
  
## General Links
* https://github.com/heptio/contour
  * Envoy-based Ingress controller deployed as a reverse proxy and load balancer 
* https://github.com/helm/charts/tree/master/stable/envoy
* https://akomljen.com/kubernetes-contour-ingress-controller-for-envoy-proxy/
* 