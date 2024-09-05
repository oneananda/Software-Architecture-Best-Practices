# 🚀 Monolith Services vs Microservices

We will discuss about the Monolith services vs Micro services and what are the key differences between them , advantages over one another, and finally specific purpose for each one.

## 🏛️ Monolith Services

In simple terms, Monolith services are widely used technology in current software world, a traditional monolith service essentially runs in a single platform, a single stack which holds all the business logic and data access logic placed in a single service, also in most cases the UI, Business Logic and Data access layers are tightly coupled and deployed in a single machine, this may be available to scale but this is strictly stick to its own stack / platform


### ✅ Advantages of Monolith

We can really get a lot of advantages for using Monolith services,

- 📜 **Single code base:** (This is an advantage until the code base isn't growing enormously)

- 🔗 No need to talk to other internal services to do a particular task as everything is available within

- 🛠️ Single stack / platform is needed for the whole team, in this case support gets easy  

- ⚙️ We can choose between the choices of "Tightly Coupled Monolith" and "Loosely coupled Monolith", this means the project can choose to deploy the services which consists of Business Logic and Data Access Layer in the same box where the UI is located or out of the box where the UI is located, in case of out of box then the services can talk to any eligible platform independent candidate for business processing.

### 📝 Examples of "Tightly Coupled" and "Loosely Coupled" Monoliths

* A service contained in the same box for UI and serves the requests, deployed in the same server (Tightly Coupled)

* A service which sits in a different box and serves to more than one UI, say Service is available to Website, Mobile App or the external services like EDI (Electronic Data Interchange) orders (Loosely Coupled)


## 📊 Real-World Example of a Monolith

An enterprise grade bug-tracking application which may highly prefer to monolith because of it's simplicity to deploy and maintainability (Initial Process)

Let's have a fictional bug tracking application "PinPointer" which prefers to have a loosely coupled monolith architecture, so they have hosted a Web API Service in a box A and hosted a Website in box B, after the successful venture into the field, the company decides to foray into the mobile app also, since they have already decoupled the Service and the UI it is easy for them to develop the Mobile App which consumes the Web API Service and process the data accordingly without any hassle.