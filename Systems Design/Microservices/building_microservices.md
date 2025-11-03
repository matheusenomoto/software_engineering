# Bulding Microservices

## Reference

**Author:** [Sam Newman](https://www.amazon.com.br/stores/Sam-Newman/author/B00LEP6IB0?ref=ap_rdr&isDramIntegrated=true&shoppingPortalEnabled=true)

**Book:** [Building Microservices: Designing Fine-Grained Systems](https://www.amazon.com/Building-Microservices-Second-Sam-Newman/dp/1492034029/ref=asc_df_1492034029?mcid=6baa8b68c0703489bc356762cb62c1d2&tag=googleshopp00-20&linkCode=df0&hvadid=709856848278&hvpos=&hvnetw=g&hvrand=4589696632486916410&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9198564&hvtargid=pla-464425939893&psc=1&language=pt_BR&gad_source=1)

<img width="123" height="155" alt="Building Microservices: Designing Fine-Grained Systems" src="https://github.com/user-attachments/assets/ea468518-6156-45d5-b91f-c38aeca8ddb6" />

## Summary
* [What are microservices](#what-are-microservices)

## What are microservices

Microservices are services that can be launched independently and are modeled based on a business domain. A service encapsulates a functionality and makes it accessible to other services across networks.

Microservices is a type of service-oriented architecture, with a clear definition of how service boundaries should be drawn. It is a technology-independent architecture.

<img width="1054" height="755" alt="microservice_example_01" src="https://github.com/user-attachments/assets/b72b09c3-2996-4047-bdc2-5734cf6edca1" />

### Concepts

**Independent Deployments**

The possibility of independent deployments is the idea that we can make a change to a microservice, deploy it, and make that change available to our users without having to deploy other microservices.

If you're going to retain only one idea from the microservice concept, it should be this: ensure you adopt the concept of independent deployments for your microservices. Get into the habit of deploying and releasing changes to a single microservice in the production environment, without having to make other deployments.

For this, it is essential that microservices have low coupling.

**Modeling based on a business domain**

