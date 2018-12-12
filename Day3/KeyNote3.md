# Kubernetes Project Update 
* Kubernetes 1.13 released last week 
* We are in the Early Majority Phase of the tech lifecycle 
* Open Standards + Extensibility 
* API Extensibility - Custom APIs + Controllers (automation engine). 
* API Policy - ex Istio policies to inject side cars into your pods
* Blog Post - Chic-Fil-A runs a K8s cluster in everyone of their restuarants (2000 in all )
    * https://medium.com/@cfatechblog/bare-metal-k8s-clustering-at-chick-fil-a-scale-7b0607bd3541
* Kubernetes is now Boring 

# IBM Cloud 
* Discussed Service Broker API from Cloud Foundry
* Serverless options in Kubernetes 
    * Knative - Build, Eventing, Serving building blocks
    * OpenWhisk - serverless abstraction

# Aqua Security - Save Yourself  
* Stay up to date in Kubernetes and your application code
* Running yaml from the Internet
    * Open a pod that is Internet accessible 
    * cat service account bearer token under secrets mount 
    * Call Kube API Server - create pods, list, pods, etc . . .
* How to prevent a service account from being creatd
    * Adminission controller. Validating Admission Controller
    * Example showing Web Hook written in Go. 300 lines of code
    * Open Policy Agent - Sandbox project 
        * No code. Rego expressions
        * Loads as ConfigMap 
* What kind of Rules Should we Create  
    * Registry Check 
    * Image Scanning 
    * Software Provenance 
* Open Source Governance 

# Kubernetes @ Airbnb 
* Reducing Boilerplate 
  * They created their own solutoin using Go Templates called kube-gen 
  * Helm ??
* Standardize on Namespaces 
  * Will be useful in scripts later on. Convention over Configuraiton 
* Generating Service Boilerplate
  * Everything about a service is in one place in git and managed by one process 
  * _infra folde in the same Git repo as your code.  
  * Make best practices default in generated configurations  ( deploy pipeline, autoscaling, docs )
* Kubectl Wrapper 
  * k tool - script called duct tape that uses ENV vars that wrap kubectl commands to make it easier for developers 
  * k ssh ENV=staging (example)
  * automate diagnostic - k diagnose 
    * Wraper for kubectl describe, kubectl get events. kubectrl logs pods 
* Admission Controllers 
  * Can do these like call a webhook in Azure Function/AWS Lambda to handle your cloud environment
* @melaniecebula 