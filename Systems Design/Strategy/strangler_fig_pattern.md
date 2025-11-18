# Strangler Fig Pattern

## Untangling the Monolith: A Guide to the Strangler Fig Pattern

In the world of software, legacy systems are like ancient, sprawling cities. They are full of history, critical to daily operations, but often burdened by outdated infrastructure, confusing layouts, and an inability to adapt to modern needs. For years, the default answer to a problematic legacy monolith was the \"big bang\" rewrite, a risky, expensive, and often-doomed attempt to replace the entire system at once.

Fortunately, there is a more strategic, less perilous approach inspired by nature itself: the **Strangler Fig Pattern**.

### What is the Strangler Fig Pattern?

Coined by renowned software expert Martin Fowler, the Strangler Fig Pattern is an architectural approach for incrementally modernizing a legacy system. Instead of replacing the entire application in one go, you gradually build a new system around the edges of the old one, piece by piece, until the legacy system is \"strangled\" and can be safely decommissioned.

The name comes from the strangler fig (or *Ficus*), a type of vine that begins its life on the branches of a host tree. It sends its roots down to the ground and slowly grows, wrapping itself around the host. Over many years, the fig becomes a robust structure of its own, and the original host tree, deprived of light and nutrients, eventually dies and rots away, leaving the magnificent fig tree in its place.

In software, the **host tree is your legacy monolith**, and the **fig vines are your new, modern services**.

### How the Strangler Fig Pattern Works: A 3-Step Process

The core of the pattern is to create a routing facade that sits between users and the legacy system. Initially, this facade simply passes all traffic to the monolith. As you build new functionality, you update the facade to divert specific requests to your new services.

Here’s the process broken down:

#### 1. Identify and Isolate
The first step is to choose a part of the legacy system to replace. A good candidate for migration is a feature that:
*   Is relatively isolated from other functions.
*   Has high business value, meaning improvements will be noticed.
*   Is frequently updated, making it a source of development pain.

Once a target is identified, you introduce a **routing facade** (often an API Gateway, proxy server, or load balancer) that intercepts incoming requests. At the start, it does nothing but forward every single request to the legacy monolith.

#### 2. Implement and Divert
Next, you build the new, modern implementation of the chosen functionality. This could be a microservice, a serverless function, or any other component built with modern tools and practices. This is one of the key benefits, you can use the best technology for the job without being constrained by the legacy stack.

Once the new service is built, tested, and deployed, you update the routing facade. It is now configured to \"divert\" requests for that specific feature away from the monolith and send them to the new service. All other requests continue to flow to the legacy system as before.

> **Example:** Imagine you want to modernize the \"user profile\" page of an old e-commerce monolith.
> 1. You build a new microservice, `profile-service`, with a modern database and a fast API.
> 2. You configure your API Gateway so that any request to `/api/user/profile` is now routed to the new `profile-service`.
> 3. Requests to `/api/products` or `/api/orders` still go to the old monolith.

#### 3. Repeat and Decommission
You are now in a loop. You continue to identify the next piece of functionality, build its modern replacement, and update the routing layer to divert traffic. With each cycle, another \"vine\" of the strangler fig wraps around the monolith.

The legacy system's responsibilities shrink over time. It receives less traffic and requires fewer changes. Eventually, all critical functionality has been migrated to new services. The monolith, now just an empty shell, can finally be turned off and decommissioned for good. The fig has completely replaced the tree.

### Why Use the Strangler Fig Pattern?

This incremental approach offers significant advantages over a \"big bang\" rewrite.

<table class=\"data-table\">
  <thead>
    <tr>
      <th scope=\"col\">Benefit</th>
      <th scope=\"col\">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Reduced Risk</strong></td>
      <td>You avoid the immense risk of a single, massive deployment failure. The system remains fully operational throughout the multi-year migration process.</td>
    </tr>
    <tr>
      <td><strong>Incremental Value</strong></td>
      <td>The business sees continuous improvement as new, faster, and more reliable features are rolled out one by one, rather than waiting years for a new system.</td>
    </tr>
    <tr>
      <td><strong>Technological Flexibility</strong></td>
      <td>It allows you to introduce modern technologies, languages, and architectures (like microservices) without being tied to the legacy stack.</td>
    </tr>
    <tr>
      <td><strong>Spreads the Cost</strong></td>
      <td>The cost of modernization is distributed over time, making it more manageable from a budget perspective.</td>
    </tr>
    <tr>
      <td><strong>Improves Developer Morale</strong></td>
      <td>Engineers get to work on new, exciting technology and see tangible progress, which is far more motivating than maintaining a creaky, old system.</td>
    </tr>
  </tbody>
</table>

### Challenges and Considerations

While powerful, the Strangler Fig pattern is not a silver bullet and comes with its own set of challenges:

*   **Data Synchronization:** This is often the hardest part. As you slice off functionality, how do the new services and the old monolith share data? Solutions can involve creating an \"anti-corruption layer\" to translate between data models, setting up database triggers, or using event-driven architectures to keep data in sync, but it requires careful planning.
*   **The Routing facade:** The routing layer is a critical piece of infrastructure. It must be highly available, performant, and well-maintained, as it can become a bottleneck or a single point of failure.
*   **Distributed Transactions:** Handling transactions that need to span both the old monolith and a new service can be extremely complex.
*   **Finding the Seams:** Identifying clean, separable boundaries (\"seams\") in a tightly coupled monolith can be difficult. Some legacy systems are so tangled that isolating a single function is a major undertaking in itself.

### Conclusion

The Strangler Fig Pattern provides a pragmatic and powerful strategy for escaping the grip of legacy technology. By incrementally replacing a monolith, organizations can modernize their systems while minimizing risk, delivering continuous value, and empowering their development teams. It’s not a quick fix but a long-term journey, one that transforms an unchangeable burden into a modern, resilient, and evolvable system, leaving the old monolith to gracefully fade away.
