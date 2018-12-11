# Securing K8S with Admission controllers 
* Dave Strebel - Microsoft Global OSS Architect 
* Challenge
    * Dynamic nature of Cloud Native Platforms (CNP)
    * Tools not adpoted for CNP
    * Not secure by default
    * Clusters not immutable 
    * Policy becomes triabl knowledge and not defined in code 
* Can try manual intervetions or restrict users 
* Admission Controller - way to extend what K8S 
    * Default admission controllers
        * NamespaceLifecycle
        * LimitRanger
        * Service Account 
        * MutatingAdmissionWebhook
        * ValidatingAdmissionWebhook
    * piece of code that intercepts a calls to the API server 
    * Authentication >> Authorization >> Mutating Admission >> Object Validation >> Validating Admission 

## Validating Webhook
* Allows you to intercept and valiate requests
* can be run in parallel as they don't mutate objects
* restrict resource creation 

# Mutating Webhook
* Executes the mutation by sending requests to webhook server
* called in serial 
* Istio inject is an example

## Policy Enforcement 
* admission control is policy based on K8s objects


## Open Policy Agent 
* CNCF Sandbox project
* policy engine 
* declarative policy language (rego)
* can be used beyond k8s for things like terraform 
* just validates json 

### Rego Policy 
* Rego is a policy language. not a programming language 
* Logic and Data 
* Rego logic is all queries 
* Write logic to search and combine json/yaml data from different sources
* Can audit policies as well 
* Gets you to immutable clusters 

# Kubernetes Policy Controller 
* Moving to OPA or as a standard. Azure developed 
* Authorization module makes it possible to implement a blacklist in front of RBAC
* Provides audting features
* 3 containes - OPA, kube-mgmt, nad controller
* Examples - whitelist/blacklist, not allow conflicting hosts for ingress, label objects based on a user from a department, block kubectl exec 
* Temp home - github.com/Azure/kubernetes--policy-controller 