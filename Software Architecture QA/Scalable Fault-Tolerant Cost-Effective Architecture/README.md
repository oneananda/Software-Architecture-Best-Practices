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





