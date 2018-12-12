# Audit in Kubernetes, the Future is here
* Basic Auditing in 1.4
  * Logged every request to the API server 
  * Every request was logged twice - one for request and its response 
* Advance Audit (alpha) in 1.7
  * Metadata and full objects in request/response 
  * JSON or text output
  * Webhook support
  * Filtering 
  * Configurable consistency 
* GA'd in v1.12
* An Audit Event
  * one event per request 
  * filled by the API Server 
  * sent to audit backend 
  * Metadata, When, Who, What 
  * stored in etcd
* Performance Impact vs Consistency 
  * Stages - when to log
  * Levels - how deep to log
    * None 
    * Metatata
    * Request
    * RequestResponse
* When creating policies 
  * Define your most generic at the bottom of the policy defintion file 
  * Define the most specific at the top of the policy file
  * Always evaluated top to bottom 
* How to send audit events
  * Flags passed to api-server 
  * --audit-log-path and --audit-webhook-config <kubeconfig>
  * --audit-{log,webhook}-mode - batch, blocking, blocking-strict 
    * batch writes logs async 
    * blocking-strict writes logs and waits for server response to finish audit 
    * Default - blocking for log and batch for webhook 
* kubernetes/community/contributors/design-proposals/api-machinery/auditing.md 
* kubernetes.io/docs/tasks/debug-application-cluster/audit 
  
## Defining a Policy 
* Today - kube-apiserver --audit-policy-file --audit-dynamic-confiuration 
* audit.k8s.io/v1
* kind: Policy 
* omitStates:
* rules

## Example
``` yaml 
apiVersion: audit.k8s.io/v1
kind: Policy
level: RequestResponse
verbs: ["get", "list", "watch"]
resources:
- group: ""
- group: "apps"
omitStages:
- RequestReceived
---
apiVersion: audit.k8s.io/v1
kind: Policy
level: Metadata
resources:
- group: ""
  resources: ["secrets", "configmaps"]
```

## Dynamic Audit Configuration 
* Issue with Policies today is it read only once at the api-server startup
* v1alpha1 in 1.13
* --audit-dynamic-configuration  option with the api-server command 
* very basic and very early stages 
``` yaml
apiVersion: auditregistration.k8s.io/v1alpha1
kind: AuditSink
policy:
    level:
    stages:
webhook:
```