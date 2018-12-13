# Deep Dive - Prometheus 
* https://sysdig.com/blog/kubernetes-monitoring-prometheus/
* Monitoring system inspired by Borgmon
* time series database 
* int64 timestamp
* not for events, logging, or tracing
  * Look at Fluentd or LogStash (as part of EFK/ELK stack) for logging 
    * https://www.fluentd.org/architecture
    * https://medium.com/tensult/the-log-battle-logstash-and-fluentd-c65f2f7c24b4
* All about metrics  
* Prometheus Server and agents 
  * Operator via CRD to automatically discover new pods/services 
  * nodeExporter (https://github.com/prometheus/node_exporter) gets host based metrics - CPU/MEM/IO
  * services/pods expose metrics over HTTP on /metrics. no need to install any agents
    * kubelet, istio, traefik expose metrics over HTTP by default 
  * For services that don't expose /metrics by default, need to use Prometheus exporter https://prometheus.io/docs/instrumenting/exporters/
* Prometheus server can be deployed as a container itself 
* Prometheus is a pull based systems 
  * Prometheus gathers them into its db
* Dashboarding via Grafana
  * What is the difference between Granfana and Kibana - https://logz.io/blog/grafana-vs-kibana/ 
* Can handle highly dynamic environments 
* One statically linked server 
* 2.0 Main features - 1yr ago
  * rewrote storage backend. Prior one time servies was write as a individual file to disk 
  * staleness handling 
  * remote read & write api is more stable-ish
* Remote Read & Write API 
  * 12 integrations for this API
  * promethus can act as a data ingrestion and then send the logs on to your own time series db
  * on going work to send write-ahead-log over the wire to fill gaps 
* will be updating Prometheus to support TLS going forward 
* 2.3.3 is the first fully stable release in the 2.x train 
  * Going to have more checks and balancers to ensure cleaner releases
  * moratorium on new features for a while
* Fixed release cycle 
  * every six weeks, we mark as a RC
  * Cycle is relative to previous RC
* long term storage is one of the last remaining major feature left untackled
  * if you need more storage, run another prometheus system but these are data islands
  * storage v3 supports backups efficiently and effectively 
  * remote read-write allows you to integrate with 3rd products
  * storage level using Thanos for object storage backends
  * Remote API can now sends WAL over the wire 
* Going towards an ACID database towards 2.8 timeframe
  * each append action gets a write ID
* Labels are encoding in our exposition format
* Spinning out Prometheus format into its own project
* https://github.com/prometheus/docs/blob/master/content/docs/instrumenting/exposition_formats.md
  * Open tracing is on board  