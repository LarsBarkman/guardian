# BOUNDED CONTEXT
> Bounded Context is a central pattern in [Domain-Driven Design](https://en.wikipedia.org/wiki/Domain-driven_design). It is the focus of DDD's strategic design section which is all about dealing with large models and teams. DDD deals with large models by dividing them into different Bounded Contexts and being explicit about their interrelationships.

Source: [BoundedContext](http://martinfowler.com/bliki/BoundedContext.html)

## What is the Domain Model?
> The Domain Model is the structured knowledge that is related to a specific problem. The Domain Model itself could be code, written prose or a diagram, the medium itself is not really important.

>The Domain Model focuses its attention on a specific problem. This constraint forces you to really get at the heart of the problem whilst ignoring everything from the outside world.

> This means that the Domain Model will have it’s own internal language that represents the important things that are specific to that one problem.

Source: [What are Bounded Contexts and Context Maps in Domain Driven Design?](http://culttt.com/2014/11/19/bounded-contexts-context-maps-domain-driven-design/)

## What is a Bounded Context?
> A Bounded Context is the boundary that surrounds a particular model. This keeps the knowledge inside the boundary consistent whilst ignoring the noise from the outside world.

>This is beneficial for a number of reasons.

>Firstly you can model the aspects of the problem without having to be concerned with other parts of the business. Using the example from earlier, a Product object within the stock system only needs to be concerned with the methods and properties of that single system, rather than any other business concern that happens to fit on an object called Product.

>Secondly the terminology within a Bounded Context can have single, clear definition that accurately describe the problem at hand. Different departments across a company will usually have slightly different ideas and definitions of similar terms, but this can often derail a project through a lack of clarity and understanding when terms are mixed.

Source: [What are Bounded Contexts and Context Maps in Domain Driven Design?](http://culttt.com/2014/11/19/bounded-contexts-context-maps-domain-driven-design/)

## What is a Context Map?
> When you start to think about the various subsystems of an application as individual Bounded Contexts, you can lose sight of the global view of the business as a whole.

> It is inevitable that the various Bounded Contexts of an application will need to communicate or share data between each other.

> A Context Map is the global view of the application as a whole. Each Bounded Context fits within the Context Map to show how they should communicate amongst each other and how data should be shared.

Source: [What are Bounded Contexts and Context Maps in Domain Driven Design?](http://culttt.com/2014/11/19/bounded-contexts-context-maps-domain-driven-design/)


## The Vision
| POLITICAL  | STRATEGIC | OPERATIONAL  | TACTICAL
|:-:|:-:|:-:|:-:|
| Customer Value-chain  |Business Capabilities And Information| Microservices| Business Services

## Further Reading
* [What are Bounded Contexts and Context Maps in Domain Driven Design?](http://culttt.com/2014/11/19/bounded-contexts-context-maps-domain-driven-design/)
* [BoundedContext](http://martinfowler.com/bliki/BoundedContext.html)
* [What is the Domain Model in Domain Driven Design?](http://culttt.com/2014/11/12/domain-model-domain-driven-design)
