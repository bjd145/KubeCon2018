# Cloud TensorFlow  
* Nathan Murthy 

# How Fast Was My Database 
* v1.4 - StatefulSets. Able to run databases 
* Emphemeral storage 
* Cloud Provider Storage Results
* Containerized Storage using Ceph/Rook or GlusterFS
* wwww.databasesoup.com

# K8S Slack Channel Administators 
* 7.5k active users
* Somebody used @everyone on Slack once. Oops
* :piece-of-cake:
* :left-shark:
* :plusone:
* :this-is-fine:

# CoreDNS over gRPC
* Yong Tang
* https://github.com/yongtang
* Limitations of DNS for Service Discovery
* CoreDNS written in go. Supports over TLS and gRPC
* Default DNS provider in 1.13
* CNCF incubating project 
* Issues 
    * DNS is UDP so not reliable 
    * Jumbo frames not utitlized 
    * No error codes so hard to diag
    * Service Error vs DNS infra error 
* CoreDNS uses gRPC to talk to the API Server and DNS from the Pod.  
* CoreDNS is configured on each node
* Scales well with layered caching 

# Use Prometheus to Autoscaling 
* Jay Evans 
* PID controller 
    * Set Point
    * process variable 
    * Error - difference between what we what and what we observe 
    * Control Variable 
* Strava - uses Mesos and Marathan 

# You got Database in my Database
* Liz Frost 
* Heptio 
* @stillinbeta
* Foreign Data Wrapper in Postgresql - can be used to call K8S API Server 
* github.com/lizfrost/k8s-fdw
