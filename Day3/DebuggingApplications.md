# Debugging Applications in Kubernetes 
* Michelle Noorali @michellenoorali
  * Co-founded Kubernetes SIG Apps
* Radu Matei @matei_radu
  * CNAB/Duffle
* For as long as we write software, we will introduce bugs

# Debugging on Kubernetes  
* Azure Dev Spaces and Google Stackdrive 
* Open Source Squash debugger 
  * solo.io 
  * Required in-cluster components 
* Why ? 
  * Too many services to run locally
  * In-cluster dependencies 

# How ?
* fmt.Println()
* What about Open Tracing / Jaegar 
* Process of Debugging 
  * Build for Debugging 
  * Create container image with new image tag
  * Update manifest 
  * Wait for pod to run 
  * Forward ports
  * Attach debugger 
* Tools 
  * KSync 
  * Telepresence - redirects traffic from your cluster to local machine 
  * Draft/Skaffold 
    * draft up
    * draft connect 
  * linkerd for Service Mesh 
    * get a side car dashboard that can see the request/response within your services 
  * Visual Studio Code with Kubernetes and Draft extensions 
    * Will port forward  and appear to attach processes inside the cluster 
* Not a single tool that can handle debugging. Visual Studio Code manages the workflow
* Future
  * Performance improvements 
  * Draft plugin for Linkerd
  * Pluggable builders and deployers 
  * Best practices for draft packs 
  * 