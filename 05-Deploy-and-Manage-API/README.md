# API Lifecycle

![API LifeCycle](/images/API-lifecycle.png)

* Runtime manager deploys API as web service
* API manager deploys proxy and policies are created - access and throttling
* API is available in API Exchange for download as a connector (OAS)
* Monitor & analyze using API visualisation, monitoring, reporting and analytics tool
* Support: Troubleshoot, scale and update for new functionality


## Deployment options
* Cloud hub VMs on AWS
    * Simplicity as managed by Mulesoft
    * Load balancing, scaling 
    * Hosted on highly available and secure servers in global datacentres
* Customer hosted runtime environment
    * Easy install for multiple applications
    * JAVA service wrapper controls JVM from OS and starts Mule
    * Runtime manager is available for both Mulesoft hosted & customer hosted Anypoint platform
* Anypoint runtime fabric - a clustered container service automates and orchestrates implememtation to chosed infra
    * Container service with Anypoint Platform control plane hosted by Mulesoft
    * Security & reliability through isolation between applications
    * Zero downtime redeployments
    * Failover through horizontal scaling
    * Containerized runtime images


## Vizualiser 
* real-time view into application architecture
    * relational diagrams dynamically updated

## Anypoint Monitoring
* Combines data across systems in application network
* Configure dashboards & alerts for preventative maintenance
* Store and search log data at scale

## Cloud Hub
* Anypoint studio has embedded connection to Runtime manager
    * Account and organisation
    * Set worker region, size and number
    * Worker is VM running in a separate container per application
    * Scale vertically by changing worker size
    * Scale horizontally by changing worker number

## API Proxies

* API Gateway runs and manages proxies to control access and usage
    * Separates orchestration from implementation concerns
    * It hosts an API or opens a connection to API on another runtime
    * Enforces policies e.g. rate limiting, throttling and caching
    * Meters traffic
    * Authorization to back end API services

API manager is interface. 

## Policies
* Rate limiting, spike control, security.
    * Custom (XML / YAML)
    * Apply multiple in set order
    * Utilise automated policies e.g. IP blacklist, basic authentication
    * SLA tiers limit #requests in specific timeframe ```Status code: 429```

## QUIZ
1. What is the purpose of API Autodiscovery?

> Allows a deployed Mule application to connect with API Manager to download policies and act as its own API proxy

2. How many Mule applications can run on a CloudHub worker?

> At most one

3. What does an API proxy application NOT do? 

> Determine which response Mule eventis allowed to pass through to the API backend service

4. What does the Mule runtime use to enforce policies and limit access to APIs?

> The Mule runtime's embedded API Gateway

5. SLA policy applied RAML spec updated with required client_id and client_secret header requirements. What is next step to gain access to API?

> Request access to API in Anypoint Exchange.
