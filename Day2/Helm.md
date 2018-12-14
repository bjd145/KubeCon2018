# Helm - An Introduction 
* Matt Farina @ mattfarina.com 
* 20 maintainers from 10 companies. 400 companies contribute code
* package manager - an easy way to share, consume, and manage applications defined by K8S resources  
* Helm v2 - released in 2016
* Helm v3 - coming soon 
```
----------------------
| Helm               |
|--------------------|
| Images|K8S Objects |
----------------------
| Kubernetes         |
----------------------
```
* Wordpress Helm chart - creates 13 K8S object 
    * helm install stable/wordpress --set wordpressBlogname="Hi cloudNativecon"
    * Wordpress Cart depends upon Mariadb chart
    * Both charts create multiple K8s objects
* Terms 
    * Helm - command line client
    * Tiller - runs in your cluster. Like an Operator 
    * Chart - a package 
    * Repository - where your charts are stored
* Files
    * chart.yaml - describes the package 
    * templates/* - directory of templates to expand into k8s objects
    * values.yaml - default values for template
    * requirements.yaml|lock - dependencies 
    * templates/tests/* - tests for charts 
        * helm test {{chart.name}}
* Template File 
    * {{- if .Values.$someValue.enabled }} #Conditional 
    * {{- end }}}
    * b64enc - extention to golang templating to base64 encode values 
* Everything gets bundled into a tarball
    * helm package . [--sign --verify]
* Other commmands
    * helm repo add http://$someUrl/ 
    * helm fetch stable/wordpress
    * helm update someAppName stable/wordpress
    * helm rollback someAppName 1 
* Stable charts are up on github.com/helm/stable
* Incubator charts are there as well 
* Helm Hub - https://hub.helm.sh - find apps that are K8S ready apps
* Monocular 
* helm/chart-testing - static analysis to validate schemas on your repos
* Plugins 
    * helm-s3
    * helm-gcs
    * helm-gpg
    * helm-diff
    * Tillerless Helmv2 
    * Azure Container Registry Helm Chart Support 
* Helm V3
    * breaking changes from lessons learned 
    * will carry almost everyone forward 