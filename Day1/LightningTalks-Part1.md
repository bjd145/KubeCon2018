# Gitops Deployment to Kubernetes
* GitOps Basic 
    * Application Repo - your application source code
    * Config Repo - contains all mainfests to configure Kubernetes
* @sakajunqaulity 
* https://github.com/sakajunquality

# Overengineering Chatbots
* Simple request -> response architecture
* Language/Platform agnostics 
* Everyone can contribute 
* http://jonathanmh.com/

# CRDs Aren't Just for Adds (Custom Resource Definitions)
* Forward looking
* TPR - started as a way to prototype 
* Gave birth to Operator patterns
    * Driven by declarative APIs
* Administion Controllers
    * Webhooks mutating and validating 
    * Schema OpenAPI v3 schema definition 
    * Declarative valiation (simple)
* Istio and KNative is build on admission controls/CRDs
* Going to Storage Snapshots, RuntimeClass, CSI, expect more
* All new APIs are CRDs and then everything will be a CRD
* Kubernetes becomes a set of operators 
* https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/

# Labels in Alerts and Better Notifications / Prometheus 
* Elena @lelenanam
* Alert >> Notifications >> external service 
* Prometheus can use golang template language {{$labels.instance}} 
* May get multiple alerts
* http://bit.ly/labels-think

# K8S Release notes
* github.com/marpaia
* You can edit you PR release-note after you PR has been marged
* Write as if you're the future. Use past tense 
* Use SIG and Kind labels 
    */kid bug, api-change, etc . . .
* Don't write notes for non-user facing changes
* Use Markdown formatting
* Grammer 

# Monitoring Kubernetes with eBPF and Prometheus
* Flow between services 
* Why - architecture, HA, Env isolation, Health, Costs 
* Getting the data
    * iptables 
    * conntrack -L
    * ss -ti
* eBPF run code kernel events. only changes, read-only, in-kernel verifier. JIT compiled
    * low overhead
* Jonathan Perry - www.flowmill.com
* Use Security with mTLS and OAuth everywhere