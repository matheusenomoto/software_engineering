# API Gateway

Basically, the API Gateway is a reverse proxy to microservices and acts as a single-entry point into the system.  It is similar to a Facade pattern from object-oriented design and similar to the notion of an “Anti-Corruption Layer” in Domain Driven Design.   It makes the processes of API design, implementation, and management considerably simpler and more consistent. The gateway helps to address some of the key concerns, including:

* How to deal with features such as security, throttling, caching and monitoring at one place
* How to avoid chatty communication between clients and microservices
* How to satisfy the needs of heterogeneous clients
* How to route requests to backend microservices
* How to discover working microservice instances
* How to discover when a microservice instance is not running

With a single-entry point into the system, it becomes easy (and manageable) to enforce runtime governance such as common security requirements, common design decisions (e.g. every consumer of the service should have X-Correlation-ID header), and real-time policies such as monitoring, auditing and measuring API usage, and throttling. The gateway abstracts microservices from their consumers, which provides flexibility to freely add or remove microservice instances to adapt to the load/demand of microservices. There may be an instance when different consumers of the service require particular data and/or have it in a special format. For example:

* An e-commerce mobile app shows product information and availability of product on the product details screen, but the desktop website version of the same e-commerce site shows recommendations, in addition to product information and availability.
* There are mobile apps where one understands XML payload and others understand JSON.

<img width="883" height="355" alt="how_a_gateway_typically_fits_into_the_overall_microservice_architecture" src="https://github.com/user-attachments/assets/a90d18f7-a31a-4642-96ed-c8b411b540db" />

## Security

Security is an important requirement of any enterprise solution. At a certain point in the architecture, the best options available for authentication, authorization, threat protection, message protection, etc. must be chosen.

### Authentication and Authorization

Federated identity is the preferred solution for implementing authentication and authorization in microservice architecture. Each microservice does not necessarily need to obtain and store users' credentials in order to authenticate them. Instead, microservices can use an identity management system that is already storing a user's identity to authenticate the user. This approach allows the decoupling of the authentication and authorization functions. It also makes it easier to centralize these two functions, to avoid a situation where every service must manage a set of credentials for every user.
image
There are three major protocols for federated identity:

* OpenID
* SAML
* OAuth.

The figure below shows the security architecture using OAuth2.0.

<img width="994" height="302" alt="security_architecture_using_OAuth2.0" src="https://github.com/user-attachments/assets/26b9a00a-a6f3-46cd-8c59-c30a49048107" />

The flow above has the potential to be a “confused deputy problem,” as every microservice is relying on the API Gateway for authentication. Ideally, every microservice should authenticate the token as received from its caller (gateway
or microservice). There is a trade-off between security and performance. The above mentioned architecture leans toward performance, as there are other mechanisms to mitigate the security risk.

The microservice architecture is part of the overall IT infrastructure for an enterprise. If the enterprise IT is cloud focused, then you should use a well-known cloud based authorization server, like Azure Active Directory or AWS IAM, which can also be integrated with on premise identity stores, like active directory. An open-source server like IdentityServer4 makes it possible to implement your own authorization server and integrate with existing identity stores.

### Threat Protection from DDoS

Most of the API Gateway provides (either integral or addon packages) features that can handle DDoS attacks, by regulating and controlling the traffic as it proceeds to backend microservices. Consider configuring the following traffic regulating parameters for the API Gateway:

* Limiting the rate of requests: Maximum number of requests an API can access within a given time frame, based on rate limiting approach. Some of the approaches are Authenticated User, Request Origin, Authenticated User, and Request Origin. For example, you might decide that an API may be accessed only once a day, by an authenticated user from a specific mobile application.
* Limiting the number of connections: Maximum number of connections that can be opened by a single client for an API.
* Closing slow connections: Time span, after which a connection will be closed from a client that is writing data too infrequently, which can represent an attempt to keep connections open as long as possible.
* Black list / White list IP addresses, if you can definitely identify valid and invalid end users of your APIs.
* Limiting the connections to backend microservices
* Blocking requests:
        o that seem to target a specific API
        o that have a User-Agent header, set to a value that does not correspond to normal client traffic
        o that have a referrer header, set to a value that can be associated with an attack
        o that have other headers with values that can be associated with an attack

### Secure Communication

It is always desirable to have SSL/TLS compliant endpoints at the API Gateway, as well as at the microservices layer, to safeguard against man-in-middle attacks, and bi-directional encryption of message data to protect against tampering.

If you are dealing with a number of certificates, then managing those becomes a huge administrative burden. There are solutions like letsencrypt.org, an AWS certificate manager, which makes it possible to transparently issue or revoke certificates. 

### Deployment Considerations

To strengthen security further, you should host all microservices on private subnet and whitelist the gateway IP at the microservices layer. If it is not possible to have microservices on private subnet, then you should validate each token with the authorization server per service call, however, this will impact performance.

## Service Registry and Service Discovery

Ease in scaling is one of the key advantage of microservice architecture. You will keep adding or removing microservice instances to adapt to incoming traffic. In addition, your teams may be adding new microservices or refactoring existing microservices into multiple (especially when moving from monolith to microservices). Service instances have dynamically assigned network locations.

### Service Registry

The service registry helps to keep track of these instances. It is a database containing the network locations of the service instances. Every service instance registers itself on start-up and de-registers on shutdown. The API Gateway uses this information during service discovery. The figure below shows service registration and discovery.

<img width="802" height="331" alt="service_registration_and_discovery" src="https://github.com/user-attachments/assets/a17a0dd3-6344-4d82-94f8-eb0e57f2ce3b" />

There are two models for checking the status of a service:

* pull model
* push model.

Although some of the registries support the pull model, it is not recommended, as it puts an additional load on the registry. Moreover, it is the service's responsibility to update the registry about its availability/unavailability to serve the request. 

### Service Discovery

The number and location of service instances is dynamic. Consequently, your client code needs to use a more elaborate service discovery mechanism. There are two main service discovery patterns: client-side discovery and serverside discovery, as shown in the figure below.

Server-side discovery is preferred for various reasons:

* It removes the discovery burden from the client so it can focus on business functions.
* If you have multiple clients, then you need to code and maintain the discovery code for each client.
* It reduces number of calls over the internet.

<img width="760" height="473" alt="service_discovery_patterns_client_side_discovery_and_serverside_discovery" src="https://github.com/user-attachments/assets/769ee79c-8a21-41fc-ba3b-d2b0fc494f05" />

## Orchestration

It is often necessary to orchestrate across multiple finegrained microservices to accomplish a business use case. As shown in the figure below, there are two options for implementing the orchestration: using the API Gateway as the orchestration layer or coding orchestration in a separate microservice.

You should avoid orchestration at the gateway layer. It violates the single responsibility principle and, in the case of scaling the API, you will have to scale the gateway along with orchestrated microservices. Some of the API Gateways have little to no capability for orchestration.

Although it is discouraged to use orchestration at the gateway layer, if you still want to use it for whatever reason, then there should not be any business logic involved while orchestrating. 
