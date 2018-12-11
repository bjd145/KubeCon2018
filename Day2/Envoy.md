# Deep Dive into Envoy Q&A
* Envoy on Kubernetes with Istio.  Memory footprint grows since each pod has the envoy container. Each container needs a copy of the configuration 
    * Answer is doing it wrong 
    * Lyft went to a declarative model to how to distribute configuration 
        * An idea is lazy load configuration  
* Use boringssl in Envoy for.
    * Thoughts about using openssl for compliance reasons (FIPS)
    * https://opensource.google.com/projects/boringssl
* QUIC is happening in 2019
* User mode TCP stack (?)
* https://www.envoyproxy.io/
* https://www.envoyproxy.io/docs/envoy/latest/intro/arch_overview/arch_overview
* Plugins with Envoy 
    * no stable API at this point. On the backlog
    * statically compiled into envoy. tied to sha 
* Envoy can be run outside Kubernetes. It's just a binary 
    * More people run it outside K8S then inside K8S
    * Istio is just a wrapper for Envoy 
* Envoy can be configured with things like retries values
    * Can be overwritten on a per request header 
* No one should try to behiding things like retries from the developer - just the implementation of how to do retries 