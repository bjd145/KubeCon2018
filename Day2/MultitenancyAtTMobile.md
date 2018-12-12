# Observability at Scale 
* Thom McCann & Amreth Chandrasehar 
* T-Mobile and MetroPCS by T-Mobile 
* 10,000 APIs across 100s of applications 
* Massive cloud native technologies over the past three years
* AWS, Azure - 6 years, 70+ apps with DC network integration. Primary AWS
* 40 container base applications using shared multi-tenant orchestration 
* Shared clusters for mulitple app teams
    * consistency across applications 
    * 7200 containers. 31b requests in Dec, 2k - 14k RPS
    * O downtime and 0 P1s - caught a lot in dev/uat 
* Created a Integrated Services platform
    * Provides - CI/CD, Logging, Telemetry, LB, DNS, Certs, Secrets, Service Discovery, etc .  .
    * Code named - Conducktor 
* Use heptio for scanning 
* JFrog - Docker repository 
* Harboer - container signing 
* Build the culture, drive towards Intelligent Ops 
    * Encourage application teams proactive engagement 
    * Begin at the beginning, don't skip steps
    * Be where developers are - cli, chat, pipelines 
    * Data Collection >> Information >> Proactive Culture >> Analytics and Intelligence Ops
        * Logging
        * Request Tracing 
        * Dashboards
        * Reports 
        * Chat Ops / Slack
        * Noise to Signal 
        * Trend Analysis 
        * Machine learning 
        * Embedded Analytics / decisions
        * Cost 
* Toolbox
    * Prometheus - 28 clusters, 1.5m metrics, 4k RPS
        * "Infinite" storage using S3
    * Grafana
        * 150 orgs, 1000+ dashboard, 820 alerts
        * Drive a DevOps culture 
    * HA/Multi-region - isolated failure domains 
    * Fluentd, ElasticSearch, Kibana, Splunk, Thanos, NATS, influxdb 
    * Created a Service Health dashboard that they may open source 
* Telemetry - Everywhere 
    * Created an internal public alert stream of clusters in slack
    * Application specific channels provides for proactive alerting and support 
    * Ingress Dashboard 
* Doing showbacks 
    * Creates a culture of cost awareness 
* Pull all the data into a Data lake. Analyzed using Spark 
    * Found CPu is not a factor for 97% of applications.  Avg utilization is 51% with a Std Deviation is 31% (wow!)
    * 600K containers in a month. 90% less than a day 