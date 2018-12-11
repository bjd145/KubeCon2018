# KubeCon Kick Off
* Aqua Security 
* 8000 people attending this year
* 4000 CKA/CKD certified 
* Projects 
    * 16 projects in incubations
    * 12 in sandbox 
* CNCF goal - Scalable application in modern, dynamic environments 
* Kubernetes Keynote will be tomorrow 
* containerd - integration with K8S went GA

## Helm 
* Welcome to CNCF
* Michelle Noorali - Software Developer @ Microsoft (https://github.com/michelleN)
* Packager Manager
* https://hub.helm.sh - discover charts across multiple repos
* Monocular - deploy search and web application 
    * https://github.com/helm/monocular
* Just release 2.12
* Helm 3 under development 
    * moving to client-side architecture
    * Lua hooks
    * Developer SDk for integration 

## Prometheus 
* Second project 
* Can handle million of data points per second 

## Fluentd
* 1.13 
* Splunk integration 
* Kinesis integratoin 

## Jaeger 
* Open Tracing is a open standard. Jaeger is an implementation of Open Tracing
* Lua Support 

## Envoy 
* 3rd project to graduate 
* Matt Klein, Constance Caramanolis
* Created from Lyft 
* Issue - lack of visibility 
* Sidecar Proxy  
    * All traffic flows this for visibiliy
* All three clouds offer envoy managed products 
    [ ] - Research 
* Why Enovy 
    * performance 
    * reliability 
    * modern - c++ codebase on github.com 
    * extensibile 
    * observbility 
    * community 
    * config API 
* Getting Involved this Week
    * CFP Track 
    * Maintainer Track
    * Hallway Track

## CoreDNS
* Replaced KubeDNS in K8S 1.13

## Linkered
* Full Service Mesh 
* Video Demo 

## Rook
* Storage provider  
* Joined sandbox in January and now an incurabtor project 

## Vitess
* v3.0
* tbd 

## gRPC
* RPC framework based on HTTP/2
* HTTP-Web
* packages.grpc.io 

## NATS
* tbd 

## Harbor 
* container repository graduating to incubator project

## etcd
* RedHat has contributed etcd to CNCF
* Build on raft - Consensus algo
* Intro - today at 11:40am 

## Full Stack Vision of Kubernetes (on GKE) 
* Aparna Sinha 
* K8S, Istio, Knative - The open cloud 
* Google - 45% contributions, RHEL - 25%, Micorosft - 3.7% (Independent Devs - 4.4%)
* 40% of the clusters in GKE run stateful applications
* Istio - service mesh based on Envoy - maps your services 
    * Birds eye view of your services 
    * observe, security, and control 
* Knative - portal, serverless framework 
    * Event supports came in 0.2
    * Don't have to worry about autoscaling, nodeport, load balancers, etc . . .
    * From source to URL 
    [] Research more 
* Knative Marketplace 

## K8s To 100,000 Enterprises
* Wendy Cartee @ Vmware 
* Business Outcomes
* Time Value of Investments 
* Opportunity costs 
* Easy on-ramp
* Integration, Automation 
* Low maintenance 
* Training and Education and Certifications 
* VMware and Open Source - Open vSwitch.
* Recently purchased Heptio 

## Phippy Goes to the Zoo
* Karen Chu and Matt Butcher @ Microsoft 
* Kids book on Kubernetes 
* Donated to CNCF.  Books and characters are now Creative Commons
* store.cncf.io or at the store 
* #PHIPPY 

# Vendors/Tools to Research 
* Rook.io - Storage
* Envoy - Ingress Controlles
* Traffik - Ingress Controllers
* Rancher - Multi-cloud / Managed clusters
* nirmata - Multi-cloud / Managed clusters
* Heptio - Multi-cloud / Managed Provider 
* Twistlock - Security  
* Knative 
* Open Policy Agent