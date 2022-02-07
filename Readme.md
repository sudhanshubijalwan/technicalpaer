# Technical paper on DDD(Domian Driven Design)

##  What is domain driven design 

Domain-Driven Design is an approach that allows the developers to write applications that will be bound to the business domain that they are going to represent. a business domain can be anything from health insurance to the railway management system.Domain-Driven Design  is a basic approach of software development that is centered around developing the programming domain model which has a very high understanding of the working of that domain.this concept was first given in a book by Eric Evans in 2003 which explains approaches through the catalog of patterns and from then the community of people have shown interest in it and also evolved this concept with their own ideas.these approaches are well suited for the conditions of complex domains where a lot of complicated and messy logic needs to be well organized.

Eric Evans's great contribution to this, through his book, was developing a vocabulary to talk about this approach, identifying key conceptual elements that went beyond the various modeling notations that dominated the discussion at the time. At the heart of this was the idea that to develop software for a complex domain, we need to build Ubiquitous Language that embeds domain terminology into the software systems that we build. While many folks talked about developing such models, they were often only done on paper, and usually expected to be done up-front. DDD stresses doing them in software, and evolving them during the life of the software product. Eric is a strong proponent of Extreme Programming and sees Domain-Driven Design as a natural component of an extreme programming approach 

## DDD Layers & Clean Architecture

There are four fundamental layers of a Domain Driven Based Solution.

* Domain Layer implements the core, use-case independent business logic of the domain/system.
* Application Layer implements the use cases of the application based on the domain. A use case can be thought as a user interaction on the User Interface (UI).
* Presentation Layer contains the UI elements (pages, components) of the application.
* Infrastructure Layer supports other layer by implementing the abstractions and integrations to 3rd-party library and systems.

## Domain Layer Building Blocks

* Entity: An Entity is an object with its own properties (state, data) and methods that implements the business logic that is executed on these properties. An entity is represented by its unique identifier (Id). Example of entities: User, Customer, Organisation..etc
* Value Object: A Value Object is another kind of domain object that is identified by its properties rather than a unique Id. Example of value objects: Name, Address, JobTitle..etc. A correct implementation of a User entity and a Name Value Object would be that the User unique identification is done by a UUID and not by the name string.
* Aggregate & Aggregate Root: An Aggregate is a cluster of objects (entities and value objects) bound together by an Aggregate Root object. The Aggregate Root is a specific type of an entity with some additional responsibilities in order to maintain the consistency of changes to objects in a model with complex associations.
* Repository (interface): A Repository is a collection-like interface that is used by the Domain and Application Layers to access to the data persistence system (the database). An example from Vernon’s book is the ProductRepository.
* Domain Service: A Domain Service is a stateless service that implements core business rules of the domain.
* Domain Event: A Domain Event is a way of informing other services in a loosely coupled manner, when a domain specific event occurs. Example from Vernon’s book: ProductReleaseScheduled is a Domain Event that a backlog product owner as a domain expert of agile project management domain cares about.