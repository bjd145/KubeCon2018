# Service Mesh Introduction 
* @christianposta
* Chief Architect  - Istio in Action author 

## Background 
* Don't forget your clients legacy systems 
* application integration 
    * Calls in parallel 
    * Aggregate messages  
    * Deal with atomicity issues 
    * Messages idempotency 
* Developers need to be aware of the network!!
* Integration is part of the app dev process 

## Ballerina - new program language 
* Built by ws02
* Strong focus on network awareness 
* For creating services and integrating 
* Built around sequence diagram model 
* Native concurrency 
* Handles all sort of application networking 
    * Retries
    * Circuit Breaker 
    * A/B testing 
    * Etc....

## Envoy Proxy 
* Service proxy that consistently solves the application networking issues 
* Live with/Colocated with App
* Istio, Consul Connect, Linkedv2
    * Istio and consul based on envoy 
    * Linkerd has their own proxy 
