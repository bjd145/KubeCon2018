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
* https://github.com/Azure/kubernetes-policy-controller
* https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/

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


# Open Policy Agent 
* CNCF Sandbox project
* policy engine 
* declarative policy language (rego)
* can be used beyond k8s for things like terraform 
* just validates json 
* Stored in a configmap (?)
* can be limited to a namespace level
* https://www.openpolicyagent.org/docs/get-started.html
* https://github.com/open-policy-agent
* Gotchas - Mutating objects need to be handled with care. They can cause expected behavior 
* Can cause latency but it's negligible fo most apps (in memory)

## Rego Policy 
* Rego is a policy language. not a programming language 
* Logic and Data 
* Rego logic is all queries 
* Write logic to search and combine json/yaml data from different sources
* Can audit policies as well 
* Gets you to immutable clusters 
* OPA Slack channel for assistnace on writing policies 

# Kubernetes Policy Controller 
* Moving to OPA or as a standard. Azure developed 
* Authorization module makes it possible to implement a blacklist in front of RBAC
* Provides audting features
* 3 containes - OPA, kube-mgmt, nad controller
* Examples - whitelist/blacklist, not allow conflicting hosts for ingress, label objects based on a user from a department, block kubectl exec 
* Temp home - github.com/Azure/kubernetes--policy-controller 
* Azure Application Gateway is in beta as a ingress controller for K8S
* https://github.com/Azure/kubernetes-policy-controller

# Demos
* Mutating Load balancer 