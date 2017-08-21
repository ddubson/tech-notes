# Serverless Concepts

* **Serverless Backend-as-a-Service \(BaaS\)**
  * app devs of mobile apps replaced monolithic servers with distributed systems of loosely coupled components in the cloud
  * Offloaded need to develop/maintain:
    * Identity
    * Authentication
    * Storage
    * etc.
  * Front-end became delivery vehicle
  * Time-to-market dropped significantly
  * Services:
    * [Google Firebase](https://firebase.google.com/)
    * [Parse Platform](http://parseplatform.org/)
    * [AWS API Gateway](https://aws.amazon.com/api-gateway/)

* **Serverless Function-as-a-Service \(FaaS\)**
  * Execute login in response to events
  * All logic is grouped into a deployable unit, called a Function
  * Packaging, deployment, scaling all handled transparently
  * Scaling is handled automatically, assuming the function is stateless
  * Use Cases
    * Proxy API credentials
    * Database queries
    * Job dispatching
    * Domain logic
  * Services
    * [AWS Lambda](https://aws.amazon.com/lambda/?nc2=h_l3_c)
    * [Azure Functions](https://azure.microsoft.com/en-us/services/functions/)
    * [IBM Bluemix OpenWhisk](https://console.bluemix.net/openwhisk/)

### Differences between FaaS and BaaS

* FaaS services are:
  * usually priced on time of execution and resource-consumption \(allocated RAM, etc.\)
  * usually spin up for the length of the execution and then shut down
* BaaS services are:
  *  usually priced on storage.
  * may be long running \(implementation detail of service provider\)



Serverless does not mean n~~o servers involved~~ - serverless means developers don't have to think about servers anymore

Offload responsibility to someone else you that you trust

Plugging into elastic computing services

* No need to provision resources \(IaaS\)
* No big planning effort \(on-prem\)
* App growth happens on-demand \(PaaS\)

## Traditional vs Serverless

![](/assets/serverless-1.png)

![](/assets/serverless-2.png)

#### Developer Challenges

* Tooling is still very rough
  * Function sprawl can impact dev workflow, cognitive load
  * Infrastructure-as-Code practices still forming
* Writing stateless code can be tricky.
  * State is offloaded to cache or db
  * If function relies on a large data set, this can be challenging



## Backend-as-a-Service \(BaaS\)

### Google Firebase

--

### AWS API Gateway

Thin layer of infrastructure, handling cross-cutting concerns:

* key management
* route definition
* request throttling
* basic caching

does not require the dev to be concerned with scale and maintenance





