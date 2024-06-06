# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*

- *Analyze costs, scalability, availability, and workflow*

|              | VM                                                                                                                                        | App Service                                                                                                                                       |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Cost         | Charge based on VM size, storages (OS, data and storage, data backup, data transfer), license, network and services                       | Charged based on plan, instance, storage, network, services                                                                                       |
| Scalability  | Adding or removing the number of VMs or scaling out and in based on demand automatically by Scale Sets                                    | Automatically scale out (add more instances) or scale up (increase instance size) based on predefined rules such as CPU, memory or request count. |
| Availability | Service Level Agreement (SLA): come with a 99.9% SLA when using availability sets, and up to 99.99% SLA with availability zones           | Service Level Agreement (SLA): offers a 99.95% SLA for apps running in the standard tier and above                                                |
|              | Redundancy options: can be deployed in availability sets or availability zones to protect against hardware failure or data center outages | Redundancy options: can be deployed in multiple regions for geo-redundancy                                                                        |
|              | Disaster recovery: can be replicated to another regions when using Site Recovery                                                          | Disaster recovery: provides built-in failover mechanisms and traffic management                                                                   |

- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

For my appropriate solution for deploying the app, both VM and App Service are good for our application, but I choose App Service for application due to:

|                                  | VM                                                                                                                                                                  | App Service                                                                                                                                             |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Environment management           | Full control of environment (OS, storage, software, license,...)                                                                                                    | Fully manage platform                                                                                                                                   |
|                                  | Suitable for applications requires OS configurations, custom software installation, legacy applications                                                             | Rapid deployment, support CI/CD                                                                                                                         |
|                                  | Rely on specific versions of software, libraries, or require custom dependencies that are not supported by PaaS solutions.                                          | Optimized for hosting web applications, RESTful APIs, and mobile backends with built-in features like authentication, custom domains, SSL, and scaling. |
|                                  | Ideal for applications requiring special configurations like custom network setups, proprietary protocols, or non-standard ports.                                   | Ideal for modern application architectures, including microservices and serverless computing                                                            | 
|                                  | Adding or removing the number of VMs or scaling out and in based on demand automatically by Scale Sets                                                              | Need automatic scaling based on predefined metrics (e.g., CPU usage, request count), reducing the need to manually adjust resources.                    |
| High Availability and Redundancy | Need advanced disaster recovery options, such as Azure Site Recovery, and the ability to configure high availability using Availability Sets or Availability Zones. | Offers built-in high availability with a 99.95% SLA for the Standard tier and above, along with automatic failover capabilities.                        |
|                                  | Suitable for applications that must run across multiple regions with intricate failover and redundancy requirements.                                                | Simplifies deploying applications across multiple regions for geo-redundancy and disaster recovery.                                                     |
| Cost                             | Charge based on VM size, software license, storage                                                                                                                  | Charged based on tier plan                                                                                                                              |

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

| VM                                                                                           | App Service                                                           |
|----------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Control over environment like OS, software, configurations that are required for application | Need a fully managed platform with minimal infrastructure management. |
| Have licensing advantages or need specific hardware configurations for legacy application.   | Modern App deployment (microservices, serverless,...)                 |                                                                       |