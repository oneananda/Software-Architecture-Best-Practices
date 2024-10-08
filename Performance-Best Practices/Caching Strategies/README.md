# Caching

Caching is the technique generally store the frequently acccessed data in an intermediate temporary place instead of server, which is typically faster and less resource-intensive than fetching the data from the original source, such as a server or database. By retrieving data from the cache instead of the server, applications can reduce load times, lower costs, and save computational resources.

## Why we need to use caching ?

The main benefits of using cahing are

- Improved performance 
By storing the frequently accessed data closer to the application significantly increases the performance of the application.

- Reduced latencey
This minimizes the delay in serving the data to the users, thus reducing the latency.

- Decreased Load on Resources: 
Caching offloads repetitive work from backend systems like databases and APIs, reducing the demand on these resources.

- Scalability: 
Caching allows applications to handle more users and higher loads by reducing the need to generate the same data repeatedly.

## Types of caching

### In-Memory Caching

Stores data in the application�s memory (RAM), making it extremely fast to access.

Use Case: Suitable for storing small, frequently accessed pieces of data such as user session information or application configuration settings.

### Distributed Caching

Stores cached data in a shared location, accessible by multiple application instances. Examples include Redis and Memcached.

Use Case: Ideal for applications running on multiple servers where consistency and availability of cached data across the entire system are important.

### Database Caching

Caches the results of database queries or frequently accessed data from the database.

Use Case: Reduces the load on the database and speeds up data retrieval for queries that are run repeatedly with the same results.

### HTTP/Response Caching

Caches HTTP responses to avoid regenerating the same response for identical requests.

Use Case: Commonly used in web applications and APIs to serve repeated requests more quickly.

### Browser Caching

Stores static assets like images, CSS, and JavaScript files in the user�s web browser.

Use Case: Speeds up page load times by reducing the need to re-download unchanged assets.

### Content Delivery Network (CDN) Caching

Distributes cached copies of static content across multiple geographically distributed servers.

Use Case: Enhances the performance of web applications by serving content from servers closer to the user's location.

## Additional Benefits of Caching

### Cost Efficiency

Caching is reducing the number of calls to database or any other storage systems, this will be useful especially in cloud environments if the billings are per usage.

### Availablity

Caching can provide fault-tolerance to some level in case of any system failure, caching can be helpful until the system back to normal.

## Considerations When Implementing Caching

### Cache invalidation 

One of the key challenges in caching in invalidating when the actual data is updated, 

Stratergies 

- Time based expiration
- Manual invalidation
- Using cache stamps

### Size management

Size management is one of the key points, if not managed correctly this will create lot of trouble instead of helping for performace,

Strategies include 

- Setting maximum cache sizes 
- Using policies like LRU (Least Recently Used) for cache eviction.

### Consistency 

Consistency between the original data and cached one is very critical, 

Techniques used

- Cache coherence protocols
- Eventual consistency model

### Security 

Securing the data and restricting access to unauthorized persons should be handled by default,

Use the following techniques

- Encryption 
- RBAC (Role based access control)

## Advanced Types of Caching

### Application-Level Caching:

This type of caching is implemented within the application code. It allows for custom caching logic based on specific business rules or scenarios.

Use Case: Caching complex computed results that are expensive to generate but frequently needed, this is the very common and easy to implement.

### Edge Caching:

Caching is done at the edge of the network, closer to the end-user, often used in combination with CDNs.

Use Case: Further reduces latency by storing cached content near the user's location, enhancing the end-user experience.

## Common Caching Strategies

### Write-Through Cache:

Data is written simultaneously in database and as well as in the caching, this ensures the cache is up-to-date

Caching the data which is not used may cost you slightly.

Use Case: Suitable when data consistency is a priority, and the application can tolerate slight performance overhead due to dual writes.

### Write-Back (Write-Behind) Cache:

Data is initially written to the cache and then asynchronously written to the database.

Use Case: Ideal for applications where performance is crucial, and the risk of data loss in case of a failure is acceptable.

### Read-Through Cache:

The application queries the cache first; if the data is not found, it is retrieved from the database and then stored in the cache.

Use Case: Useful when the cache is expected to have a high hit rate, minimizing database access.

### Cache-Aside (Lazy Loading):

The application queries the cache, and if the data is not present, it retrieves it from the database and populates the cache.

Use Case: A common strategy where the cache is only populated with data as needed, reducing unnecessary data in the cache.

