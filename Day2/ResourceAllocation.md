# Getting the Most out of Kubernetes - Optimizing Cluster Resoure Allocation in Prod
* @hjharnis - Staff Engineer @ Zeit
    * Slides on github  - https://github.com/hharnisc/hharnisc.github.io
    * https://github.com/hharnisc/kubernetes-resource-optimization-demo
* Understand Requests and Limits 
* Buffer - social management software 
    * Simple Node application with Dynamodb backend 
    * Manually verified with curl 
    * Monolith application 
* Journey to Kubernetes Resource Limits 
* 1% shift from monolith to microservices 
    * Shifted 10% then 50%. Ooops. Dumpster fire 
    * Tried 5x pods - scale to 20 pods.  Helped but pods dyed 
* OOMKiled 
* Resource Limits - upper limit on a container resource 
    * Container run wiht unbounded CPU and memory limits 
    * K8S will restart the container if resources limits are hit
* Resource Requests - allocated resources for a container 
    * containers may be throttled back down to request when exceeded 
    * bursty behavior 
    * matches limit if no requests set explicitly 
* QOS: Guaranteed - Highest Priority 
* QOS: Burstble 
* QOS: Best Effort. Lowest Priority 
* Optimal*Limits 
    * Pods have enough resources to complete their task 
    * Nodes run maximum number of pods
* Way to Get these Wrong 
    * Under-allocation 
    * Over-allocation 
* Optimal 
    * Want to strive for but hard to get. Lean towards over-allocation 
    * Maybe get 90% optimal 
* cAdvisor <-> Heapster 
    * gather all the metrics 
    *  cAdvistor connects to docker sockers. Pull metrics. Every 10-15 seconds 
        * Provides interface for kubelet to pull those metrics 
    * kubelet will make decision on what to do based on the metics 
    * Heapster collects metrics from all the kubelets to different storage backends 
        * Deprecated in 1.11
        * Suggestion to move to Metrics + Prometheus 
* Setting looks something like 
    * cpu: 100m #~1/10th of a core 
    * memory: 50Mi # 50 Mebibytes 
* Set limits and then load test until the pod crashes on resource limit outage 
    * Duration test under load at 90% limit to see how memory leaks and other overflows may be affected 
* loader.io
* kubescope - https://github.com/hharnisc/kubescope-cli
* Don't forget about k edit deployment - instead of always editing your yaml . Quick and Dirty 
* Keep a fail log 
    * memory is slowly increasing 
    * CPU pegged at 100%
    * 500s
    * High response time 
    * Dropping requests 
    * Queuing 
* Breakfix testing 
* Horizontal Pod Autoscaler - Change Deployment replica count based on a metric (scale up or down)
* Vertical Pod Autoscaler (Alpha) - Change Pod resource requests in place and restart the pod 
* Datadog 