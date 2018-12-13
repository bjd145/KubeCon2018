# General Thoughts 
* Kubernetes is now in the boring phase. 
    * Focus on scale, security, and manageability 
* Service Mesh was everywhere
    * Lots of talks on Envoy and lots of questions on Istio
* Observability was a close second 
    * Open Tracing
* Startups are still figuring things out
    * They differ from Enterprise in their willingness to experiment and trust in their employees. 
    * Forward looking Enterprises like Nordstrom, Home Depot, CapitolOne, T-Mobile, and Walmart are using k8s
        * Not only that but they are giving back to the community in terms of open source software
* Open Policy Agent - this is a Sandbox project but will be key for more Enterprise adoption 
* Declarative >> Imperative
* Projects everywhere in CNCF that reproduce what cloud providers already do
    * No Lock in is key.
    * Azure Examples
        * Prometheus <<>> Azure Container Monitor / LogAnalytics 
        * Jaeger <<>> Application Insights 
        * Grafana <<>> PowerBi 
        * Others KubeMQ, OpenEBS/Rook, 
* Lots of interest in Operators 
    * This will really allow complex applications using Stateful pods to run in k8s
    * Azure just released an operator to configure SQL Server Always On
* Serverless on k8s is on the horizon
    * Scale to Zero 
    * Trigger Starts
    * Looking at AWS Lamdba for imspiration 
* Love the focus on Community but really do I get involved ? 
* Some of the best presenters did have the most polish decks.  Lots of screen captures of digtial whiteboards. 

# Tooling 
* No Windows machines anywhere - even the Microsoft employees went out of their way to show off their Macs.
    * No Linux Subsystem. Boo.
* Visual Studio Code was everywhere! 
* Programming language of choice in Demos - Go followed by Python
* Everyone is still using GitHub to host their code repositories.
    * No one mentioned Azure DevOps as a CI platform, not even Vendors 
* No one seems to like creating k8s yaml configuration files.  
    * Everyone is creating their own tool though very intereted in Helm 