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

<img width="642" height="396" alt="cache_aside_lazy_loading" src="https://github.com/user-attachments/assets/9af54c6c-f3f4-45d8-98d1-406aa6516a04" />

**Read-Through**

How it works: The application treats the cache as the primary source. On a cache miss, the cache fetches from the original source itself.

**Pros**: Cleaner application code.

**Cons**: Requires cache providers that support this (e.g., Redis modules, Hazelcast).

<img width="642" height="397" alt="cache_read_through" src="https://github.com/user-attachments/assets/507b5bac-4e0a-424b-b35a-d251c5e4d976" />

**Write-Through**

How it works: When data is written/updated, it is written to both cache and original source simultaneously. The operation only completes when both succeed.

**Pros**: Strong consistency between cache and source. No data loss.

**Cons**: Higher write latency since two synchronous operations are needed.

<img width="642" height="372" alt="cache_write_through" src="https://github.com/user-attachments/assets/ef87519a-85d5-4202-beda-f8d5862672d3" />

**Write-Back (or Write-Behind)**

How it works: The application writes only to the cache (very fast). The cache then writes asynchronously to the original source, after some time or batch size.

**Pros**: Extremely low write latency. Ideal for write-heavy systems.

**Cons**: Risk of data loss if the cache fails before persisting to the source.

<img width="642" height="340" alt="cache_write_back" src="https://github.com/user-attachments/assets/3e3b694b-d971-4510-aaf0-d81a8b7a363a" />

**Ways to Apply Caching**

Full-Page Cache: Store the complete HTML of a page. Best for static or lightly personalized pages, like a blog homepage.

Fragment Caching: Store parts of a page, such as a header, footer, or “recommended products” widget. Useful for dynamic pages with static sections.

Data/Object Cache: The most granular approach. Store serialized objects or data structures, like a user profile JSON or product details.

**Adapting Legacy Systems**

Adding cache to a legacy system requires caution:

Identify Bottlenecks: Use monitoring (APM) to find slow, frequent DB queries or API calls. These are prime cache candidates.

Isolate Data Access: Refactor code so all access to an entity goes through a single layer (e.g., a Repository or Service). Makes cache integration easier.

Choose Invalidation Strategy: The most critical part.
- TTL (Time-To-Live): Simplest option. Data expires after a fixed time (e.g., 5 minutes). Acceptable if slight staleness is tolerable.
- Explicit Invalidation: When data updates (e.g., UPDATE product SET price = 100), code explicitly removes the cache entry.

Gradual Implementation: Start with low-risk, high-read data (e.g., country list, product categories). Don’t try caching everything at once.

Add Monitoring: Build dashboards for cache hit ratio. A high ratio (above 90%) means cache is effective.

**When to Use Cache**

Read-Heavy Data: Data read far more often than written (e.g., blog posts, product catalog, videos).

Expensive Computations: Store results of CPU- or time-intensive operations (e.g., complex reports, recommendation engines).

Static or Semi-Static Data: Rarely or never changing info (e.g., list of states, app configurations).

Reduce External API Calls: Avoid rate limits or third-party costs.

Improve User Experience: Whenever fast response times are critical for user satisfaction.

**When NOT to Use Cache**

Write-Heavy Data: If data changes on every read or very frequently, invalidation costs may outweigh benefits.

Critical Real-Time Data: For data where strong consistency is mandatory (e.g., bank account balances, flight seat availability, live auction bids).

Simple Low-Traffic Systems: Cache overhead may not justify performance gains.

Unique Per-Request Data: If each request fetches completely different data, cache hits won’t occur, making caching useless.

