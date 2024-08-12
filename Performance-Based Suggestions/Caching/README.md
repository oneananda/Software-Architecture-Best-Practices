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

Stores data in the application’s memory (RAM), making it extremely fast to access.

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

Stores static assets like images, CSS, and JavaScript files in the user’s web browser.

Use Case: Speeds up page load times by reducing the need to re-download unchanged assets.

### Content Delivery Network (CDN) Caching

Distributes cached copies of static content across multiple geographically distributed servers.

Use Case: Enhances the performance of web applications by serving content from servers closer to the user's location.