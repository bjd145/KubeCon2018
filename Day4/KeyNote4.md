# SRE at Uber - Improving Operational Experience : Smooth Operator
* m3db - distributed time services db
* Aggregator and Query Engine
* Prometheus Sidecar
* 2018 - Uber runs 40+ clusters with 10+ configurations
* 20x growth in the number of clusters but engineers stated the same 
* Sharing and replications (3) across fault domain 
* Lifecycle - reactive vs proactive 
* Use AWS and GCP
* Managing complexity 
* Runs across multi-cloud and on-premise 
* require performant stateful primitives 
  * need to be query from a few minutes or few years
  * remote block store - increased latency and less portable 
* Operators - see below
* m3db.io/talks 
* Kubernetes - persistent local storage primative 
* Node Affinity + Statefulsets 
* m3db-operator 
  * Operator can hande when node outage.  
  * Operator pushes a new desire state to k8s - same pod in stateful but with new storage (m3db handles the data replication)
* instance identity != host 

## Advice for Large Stateful Workloads
* make sure your workload works well outside of k8s before putting it on k8s
* declarative > imperative which is core to k8s.
  * Operator just exchange desire states with k8s and want for desire state to converge
* iterate on each stateful iteraction 
  * don't try to do everything at once 
* Investigating autoscaling and multi-region 

# k8s - Living up to Hype 
* k8s has lived up to hype! 
* Why?
  * Built off over a decade worth of work from Google 
  * User Focused 
    * Kelsey Hightower - When your engineers have the same problems as the people they are building things for, watch how fast things get fixed
  * Declarative API centric model with automation 
    * Imperative - manual driving. declarative - autopilot 
  * Kubernetes runs anywhere 
  * Community 
* What's next?
  * Quality. A focus forever.
    * Better enterprise features
    * Better upgrade process 
  * Experience 
    * HTTPS Deployment  
    * Debug services 
  * Conformance 
    * ensure k8s is the same across all service providers 
    * forking 
  
# Maturing Kubernetes Operators 
* Rob Szumski 
* Adoption Phases 
  * Stateless Applications
  * Stateful Applications
  * Distributed Systems (today)
    * Data Rebalancing 
    * Autoscaling 
    * Seamless upgrades 
* Operators
  * Embed ops knowledge from the experts
    * Runbook or Wiki 
    * Whatever it takes to run your application that can be modeled in software  
  * Operator v1.12
  * deployments, stateful, stateless manifests 
* Operators for all
  * truly hybrid 
  * uniform deploy and debug
  * no reinvention of core concepts
  * flexible
* Operator Lifecylce 
* Operator metering 
* Links
  * https://github.com/operator-framework
  * https://coreos.com/blog/introducing-operator-framework
  * https://cloudblogs.microsoft.com/sqlserver/2018/12/10/availability-groups-on-kubernetes-in-sql-server-2019-preview/ 
  * https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-kubernetes-deploy?view=sqlallproducts-allversions
  * https://www.mongodb.com/blog/post/introducing-mongodb-enterprise-operator-for-kubernetes-openshift
  * https://github.com/GoogleCloudPlatform/spark-on-k8s-operator

# Kubernetes and the Path to Serverless
* Kelsey Hightower @ Google 
* amazing things that you can accomplish when you free up your team to do what they are best at
* scale to zero.
* triggers
* Learn from AWS Lamdba 
* Can you upload a container up to AWS lamdba 
  * extract binaries from tarball that is the docker container 