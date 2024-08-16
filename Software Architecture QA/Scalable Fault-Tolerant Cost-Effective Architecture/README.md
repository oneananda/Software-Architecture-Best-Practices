# Building Scalable, Fault-Tolerant and Cost-Effective Architecture

## Question 

How will you build Scalable, Fault-Tolerant and Cost-Effective Architecture for an application which handles milions of transactions per day?

We need to ensure the 

- High availablity
- Data consistency
- Minimal lateny 

for all the users which spans across different continents.

- What are the key components you suggest ?

- What are the technologies availabe ?

- What are the general considerations for bulding such architecture ?

### Answer

Key components and technologies

**Cloud Provider:** We can choose any of the following leading cloud providers

- Amazon Web Services
- Azure Cloud
- Google Cloud

Please check in the following comparision table for detailed analysis : https://github.com/oneananda/Software-Architecture-Best-Practices/blob/main/Software%20Architecture%20QA/Scalable%20Fault-Tolerant%20Cost-Effective%20Architecture/Cloud%20Services%20and%20Key%20Components%20Comparison.jpeg

**Load Balancing:** Deploy any load balancing services

- AWS Global Accelerator
- Azure Front Door
- Google Cloud Global LoadBalancer

This is to direct traffic to the nearest regional data center, ensuring low latency and high availability.

**Microservices Architecture:** (Optional)

Break down the application into microservices, each responsible for a specific business function (e.g., user management, product catalog, payment processing). This allows independent scaling and easier management.

**Containerization and Orchestration:** 

Use Docker for containerization and Kubernetes (or AWS EKS/Azure AKS) for orchestrating the microservices. This provides portability and efficient resource usage.Containerization and Orchestration: Use Docker for containerization and Kubernetes (or AWS EKS/Azure AKS) for orchestrating the microservices. This provides portability and efficient resource usage.

**Data Storage Options:**

- Relational Database: 
Use a distributed database like Amazon Aurora Global Database or Google Cloud Spanner for transactional data, ensuring global consistency with multi-region replication.
- NoSQL Database: 
Implement a NoSQL database like DynamoDB or Cosmos DB for handling user sessions, and other high-velocity data. Ensure that data is replicated across regions.
- Cache Layer: 
Use a distributed cache like Redis or Memcached to store frequently accessed and infrequently updated data, reducing load on the databases and improving response times.

Example: `User session data, Static pages, Product catalog information`

**Content Delivery Network (CDN):** 

Use a CDN like Amazon CloudFront or Azure CDN to serve static content (e.g., images, CSS, JS) closer to the user, reducing latency.

**Event-Driven Architecture:** 

Implement an event-driven model using a message broker like AWS SQS/SNS, Azure Service Bus, or Kafka for asynchronous communication between microservices, improving scalability and decoupling services.

**Auto-scaling:** 

Set up auto-scaling policies for both the application layer and the database to automatically adjust resources based on traffic and usage patterns.

**Security:**

- Encryption : Implement E2E encryption for data in transit (eg TLS) and in the rest (AES-256)
- IAM Policies: Enforce strict identity and access management policies, using least privilege principles.
- WAF and DDoS Protection: Use Web Application Firewalls (e.g., AWS WAF, Azure WAF) and DDoS protection (e.g., AWS Shield, Azure DDoS Protection) to secure the application against attacks.

**Monitoring and Logging:**

- Centralized Logging: Use a centralized logging system like ELK Stack (Elasticsearch, Logstash, Kibana) or Azure Monitor to collect and analyze logs from all microservices.
- Monitoring: Implement monitoring tools like Prometheus, Grafana, or AWS CloudWatch for real-time performance tracking and alerting.

**Disaster Recovery and Backup:**

- Multi-Region Deployment: Setup the services in multi region setup to get the failover scenario and DR (Disaster Recovery)
- Backups: Regularly back up databases and critical data using automated backup services (e.g., AWS Backup, Azure Backup) and store them in a separate region.

**Cost Optimization:**

- Reserved Instances and Spot Instances: Use a mix of on-demand, reserved, and spot instances to optimize costs based on predictable and variable workloads.
- Serverless Services: Utilize serverless technologies (e.g., AWS Lambda, Azure Functions) where applicable to reduce operational overhead and costs.

These are the general considerations for the above question, we can customize based on our needs if any specific cloud provider is preffered.

## Question 

How can you customize the same requirement based on AWS Services ?

### AWS Architecture Layers

## 1. Compute Layer

- **Amazon EC2 (Elastic Compute Cloud):** Central to the architecture, providing scalable compute capacity.
- **Amazon ECS / EKS (Elastic Container Service / Elastic Kubernetes Service):** For containerized workloads, supporting both Docker containers and Kubernetes orchestration.
- **AWS Lambda:** For serverless computing, handling event-driven processes without managing servers.

## 2. Storage Layer

- **Amazon S3 (Simple Storage Service):** Object storage for storing and retrieving any amount of data, often used for backups, archival, and serving static content.
- **Amazon EBS (Elastic Block Store):** Block storage volumes attached to EC2 instances for persistent storage needs.
- **Amazon EFS (Elastic File System):** Managed file storage for shared access across multiple instances.

## 3. Database Layer

- **Amazon RDS (Relational Database Service):** For relational databases such as MySQL, PostgreSQL, Oracle, and SQL Server, managed by AWS.
- **Amazon DynamoDB:** A fully managed NoSQL database service for high-performance applications.
- **Amazon Redshift:** Data warehousing service for large-scale data analytics.

## 4. Networking Layer

- **Amazon VPC (Virtual Private Cloud):** Core networking service that enables you to create a logically isolated section of the AWS cloud.
- **Amazon Route 53:** DNS web service for domain name management.
- **Amazon CloudFront:** Content Delivery Network (CDN) for delivering content with low latency.
- **Elastic Load Balancing (ELB):** Distributes incoming traffic across multiple targets (EC2 instances, containers, IP addresses).

## 5. Security and Identity Layer

- **AWS IAM (Identity and Access Management):** For managing users, groups, and roles with defined access policies.
- **AWS KMS (Key Management Service):** For managing encryption keys across your services.
- **AWS WAF (Web Application Firewall):** Protects your web applications from common web exploits.

## 6. Monitoring and Logging Layer

- **Amazon CloudWatch:** Monitoring service for real-time operational data, such as logs and metrics.
- **AWS CloudTrail:** Provides governance, compliance, and operational and risk auditing of your AWS account.

## Question 

How can you customize the same requirement based on Azure Cloud ?

**Global traffic management**

-**Azure Front Door** : This service will do the global load balancing and routing traffic to the nearest data center, provides
	- SSL Offloading : Outsourcing the encryption to a separate service
	- Caching : Stores frequently used data in a nearest accesible place
	- Fast fail over : Quickly fail over when needed
	- Improves High availablity
	- Reduces latency

-**Compute Layer** :
	- Azure VMs : Use Azure Virtual Machines.
	- Azure VMSS : Azure Virtual Machine Scale Sets, a set of VMs for non-containerized workloads, leverage VMSS to automatically scale the number of VMs based on demand.
	- AKS: Azure Kubernetes Service, use AKS for containerised environment and use it for orchestracting containers, especially for microservices architecture, this will be used to deploy, manage and scale applications easily across different regions.