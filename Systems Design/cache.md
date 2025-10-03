# Cache

Caching is one of the most fundamental and effective techniques to optimize the performance, scalability, and resilience of systems. It consists of storing a copy of data in a faster-access location than the original source, preventing costly operations (such as database queries or external API calls) from being executed repeatedly.

**Cache**

Cache is a high-speed data storage layer that keeps a subset of data, usually transient, so that future requests for the same data can be served faster than by accessing the primary storage location.

The main goals are to reduce latency and decrease load on the original source (backend), improving overall system performance.

Practical example: Imagine checking the profile of a popular user on a social network. The first request retrieves the data from the main database (slow operation). The system then stores a copy of that profile in an in-memory cache (fast operation). For the next thousand users requesting the same profile, the system serves it from the cache, avoiding a thousand database queries.

**Types of Cache**

Caching can be implemented in different layers of an architecture.

**Client-Side Cache**

What it is: The cache is stored on the user’s own device. The most common example is browser cache, which stores files like images, CSS, and JavaScript.

Example: When you visit a website, your browser downloads the logo and saves it. On another page of the same site, the logo is loaded from local cache instead of being downloaded again.

**CDN Cache (Content Delivery Network)**

What it is: A geographically distributed network of servers that stores copies of static content (images, videos, etc.) from a site. Content is delivered from the server closest to the user.

    Example: An e-commerce company in Europe uses a CDN. When a user in Brazil accesses the site, product images are served from a CDN server in São Paulo instead of one in Frankfurt, drastically reducing latency.


**Server-Side Cache**

This is the most common type in system design and can be divided into:

In-Memory Cache (Application-Level): Data is stored in the application server’s RAM. It’s extremely fast but limited to available memory and not shared between multiple application instances.

    Example: A Java app may use a library like Caffeine or Guava Cache to store in memory a list of product categories that rarely change.

Distributed Cache (External): A separate, centralized service optimized for caching, accessible by multiple application instances.

    Example: Several microservices in a checkout system use a Redis or Memcached cluster to store user session data, ensuring session consistency across different servers.

**Database Cache**

What it is: The database itself has internal caching mechanisms to speed up queries, storing frequently executed query results or disk data blocks in memory.

    Example: A database like PostgreSQL keeps recent queries and execution plans in shared memory to accelerate future executions of the same query.

**Advantages**

* Reduced Latency: Much faster responses for the end user.
* Reduced Backend Load: Fewer accesses to databases, APIs, and other systems, allowing them to operate more efficiently.
* Increased Scalability: The system handles higher traffic without proportionally scaling backend infrastructure.
* Higher Availability: If the primary data source (e.g., database) becomes temporarily unavailable, the system can still operate in a limited way by serving cached data.
* Cost Savings: Lower computational resource usage (CPU, I/O) on the backend can reduce infrastructure costs.

**Disadvantages**

* Cache Invalidation Complexity: The famous saying goes: “There are only two hard things in Computer Science: cache invalidation and naming things.” Ensuring the cache is cleared when the original data changes is a tough challenge.
* Data Consistency: Cached data may become stale if the original source updates and the cache doesn’t. This can result in showing incorrect information to users.
* Increased System Complexity: Adds a new layer to the architecture that must be managed, monitored, and maintained.
* Single Point of Failure: If a centralized distributed cache fails, it can take down all applications relying on it. High-availability strategies for cache are necessary.

**Cache Strategies (Categories)**

Strategies define how and when data is read and written to the cache.

**Cache-Aside (Lazy Loading)**

The most common strategy.

How it works:
The application first looks for data in the cache.
If found (cache hit), it returns the data.
If not found (cache miss), the application fetches from the original source (e.g., database).
After fetching, it stores a copy in the cache and returns the data.
    
**Pros**: Cache stores only requested data.

**Cons**: The first request for data is always slow (cache miss).