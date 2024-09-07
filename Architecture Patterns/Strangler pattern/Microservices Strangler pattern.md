# Microservices Strangler pattern - Uses and Steps

The Strangler pattern is a technique used to gradually migrate a monolithic application to a Microservices-based architecture. It involves creating new services to replace specific functionalities of the monolithic application, while leaving the rest of the application intact. The new services are gradually "strangled" around the existing monolithic codebase, until the entire application is replaced by a set of Microservices.

Steps to implement the Strangler pattern with Microservices:

    Identify the functionalities of the monolithic application that are good candidates for migration to Microservices. These are typically functionalities that are tightly coupled to a specific subset of the application's data and have a clear, well-defined set of inputs and outputs.

    Create new Microservices to replace the identified functionalities. These Microservices should be loosely coupled to the rest of the application and have a clear, well-defined API.

    Decouple the new Microservices from the monolithic application by creating an API gateway or a reverse proxy that routes incoming requests to the appropriate service.

    Gradually replace the monolithic code with calls to the new Microservices. This can be done by creating new endpoints in the monolithic application that invoke the corresponding Microservices.

    Monitor the performance of the new Microservices and the monolithic application to ensure that the migration is not causing any negative impact.

    Repeat the process of identifying functionalities, creating new Microservices, and replacing the monolithic code until the entire application has been migrated to a Microservices-based architecture.

 Strangler pattern is a gradual process that can take a long time to complete, depending on the size and complexity of the monolithic application.