# Run Kubernets in Production When You Don't know What You Don't Know 
* Understand the design of the software you are using 
* Run gamedays / breakfix tests 
    * Try in QA and some in production 
    * Things like destory your API server, destory etcd cluster ....   
* Classify your possible production issues then 
    * Pods won't start ... Think of all the reasons why 
* Have production issues only once 
* Fix Categories of your Issues
* Share Knowledge ! 
* What if I can't what caused the incident 
    * It's an opportunity
* Make incremental traffic 
    * 5% traffic or non-critical service
    * establish interface boundry 
    * No haunted forests 
* Don't expose Kubernetes to developers 
    * Reduce Cognitive load for them 
    * github.com/stripe/skycfg ... skycfg.fun 
* Always have a rollback plan 
* Culture 
    * You don't have to be an expert at the beginning but you need to become one 
    * build an engine of learning 
    * building that expertise takes time! 
    * Managers - make space for your team to learn 