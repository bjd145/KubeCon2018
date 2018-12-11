# Spawning K8S in CI for Integration Tests
* Marko Mudrinic 
* kind - a tool for running local kubernetes clusters using Docker 
* Only requirement is Docker 
* pre-built Docker image containing all dependencies 
* Clusters are provisioned using kubeadm - single node
* github.com/xmudrii/travis-kind
* Steps
    * go get sigs.k8s.io/kind
    * kind create cluster
    * export KUBECONFIG="$(kind get kubeconfig-path)"
* kind create container with another Docker inside 
* How to pass controller's image to Docker running inside kind's container
* Option - side load 
* Native Feature - work in progress #28 (kind repo)
* sigs.k8s.io/kind

# K8S in the Federal Gov't
* John Osborne
* Risk Management Framework - everyone must go through this before code is pushed to production 
    * ATO - Authority to Operate 
    * 16 - 18 months to go through 
* 18F - startup with the federal gov't
    * Compliance as code effort
    * Standard format to generate paperwork
* Red Hat - generate paperwork and automated compliance with Ansible 
* http://bit.ly/k8sato

# Optimizing Networking
* Datadog - 1000 - 2000 nodes. Trilions of data points. Multiple clusters
* IPVS instead of iptables
* No bridging. Route on hosts 
* Native pod routing.  Pod get standard IPs. No overlay overhead
    * AWS EKS CNI plugin or Lyft CNI plugin
    * GCP IP aliases 
    * On-premise - BGP. Calico Kube-router
* ExternalTrafficPolicy: Local
    * Only send traffic to node where the pod is running but all nodes are still in the LB
    [ ] - Need to review
* Native Pod routing 
    * Can be configured to only send traffic to node where the pod is running and LB doesn't need to be configured with all the nodes in the cluster
* No reference to Azure. 

# gRPC-Web
* Stanley Cheung
* C# has client libraries 
* client application has stub .proto definitions that defines your contract to your service 
* Work is being done to work with browsers to have gRPC functional
* gRPC-Web is an aux protocol providing a translation layer between browswer and gRPC
* Based on Envoy 
* Under development.GA since 10/2018
* github.com/grpc/grpc-web

# Distributive Tracing 
* Shreya Sharma 
* Dapper Paper - Google paper on distributive tracing 
* 3 Ids
    * Trace Id - End to End ID
    * Span Id - The individual component 
    * Parent Span Id - whom talks to whom
* Haystack - Expedia created this solution for tracing 
    * Like Jaegar

# Humans and AI 
* Kendall Miller
* @blatantterror 
