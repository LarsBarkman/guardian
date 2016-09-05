---
title: Dealing With Legacy
keywords: Legacy
sidebar: framework_sidebar
permalink: dealing-with-legacy.html
toc: true
summary:
---

<br>
> "Let's face it, all we are doing is writing tomorrow's legacy software today. By making it easy to be strangled in the future, you are enabling the graceful fading away of today's work."
<br> -- Martin Fowler

## What Is a Legacy System?
> In computing, a legacy system is an old method, technology, computer system, or application program, "of, relating to, or being a previous or outdated computer system." Often a pejorative term, referencing a system as "legacy" often implies that the system is out of date or in need of replacement.
> While this term may indicate that some engineers may feel that a system is out of date, a legacy system may continue to be used for a variety of reasons. It may simply be that the system still provides for the users' needs. In addition, the decision to keep an old system may be influenced by economic reasons such as return on investment challenges or vendor lock-in, the inherent challenges of change management, or a variety of other reasons other than functionality. Backward compatibility (such as the ability of newer systems to handle legacy file formats and character encodings) is a goal that software developers often include in their work.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Legacy_system)

## Which Systems Are Legacy Systems?
* Which systems that are is legacy or not is subjective and it's impossible to give an exakt difinition
* One general guidence is "The effort and/or cost to transform the system to [Cloud Native](being-cloud-native.html) is to great to be worth it or transformation is just not possible"

## The Law of Holes
> The first law of holes, or the law of holes, is an adage which states that "if you find yourself in a hole, stop digging". The meaning behind it is that if you find yourself in an untenable position, you should stop and change what you are doing, rather than carrying on and exacerbating the situation.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Law_of_holes)

## How To Handle Legacy Systems?
* Follow the "Law of holes" and stop digging!
* Legacy systems should only be maintained
  * Don't implement new functionality (improvements on current functionality is ok) in the legacy system
* Focus on stability and cost efficiency
  * Changes must not jeopardize the stability of the system
  * Changes must focus on stability and cost efficiency
  * All changes to infrastructure, tools and code must be justified based on maintenance alone
* The legacy systems should be "made irrelevant" not changed, with the use of
  * Strangler Pattern
  * Facade Pattern
  * (Possibly) API Gateway Pattern

## Strangler Pattern
> "The most important reason to consider a strangler application over a cut-over rewrite is reduced risk. A strangler can give value steadily and the frequent releases allow you to monitor its progress more carefully. Many people still don't consider a strangler since they think it will cost more - I'm not convinced about that. Since you can use shorter release cycles with a strangler you can avoid a lot of the unnecessary features that cut over rewrites often generate."
<br> -- Martin Fowler

Source: [Martin Fowler](http://www.martinfowler.com/bliki/StranglerApplication.html)

## Facade Pattern
> The facade pattern (or façade pattern) is a software design pattern commonly used with object-oriented programming. The name is by analogy to an architectural facade.
> A facade is an object that provides a simplified interface to a larger body of code, such as a class library. A facade can:
> * make a software library easier to use, understand and test, since the facade has convenient methods for common tasks;
* make the library more readable, for the same reason;
* reduce dependencies of outside code on the inner workings of a library, since most code uses the facade, thus allowing more flexibility in developing the system;
* wrap a poorly designed collection of APIs with a single well-designed API.
> The Facade design pattern is often used when a system is very complex or difficult to understand because the system has a large number of interdependent classes or its source code is unavailable. This pattern hides the complexities of the larger system and provides a simpler interface to the client. It typically involves a single wrapper class which contains a set of members required by client. These members access the system on behalf of the facade client and hide the implementation details.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Facade_pattern)

## Putting The Strangler And Facade Pattern To Practical Use
* The Strangler Pattern must be controled by the new development
* New development must be greenfield ([Being Cloud Native](being-cloud-native.html)) i.e. it should not have any knowledge of the legacy systems except for the facade
* A Facade Pattern must be implemented by the legacy team to hide the legacy system

## Implementing A Facade Pattern With API Management
* This applies **ONLY** to legacy systems that can not expose APIs according to [Cloud Native](being-cloud-native.html)
* API Management hides the complexity of the legacy systems and make them look and feel [Cloud Native](being-cloud-native.html) while at the same time not forcing them to change their methods of integration
* The API Management system **MUST NOT** be used as part of ANY greenfield development

## Implementing Strangler Pattern With Only A Request Reuter
* In the best of all worlds the request coming in is a http request and in that case it's preferable to implement the strangulation via a Request Reuter
* A Request Reuter can be a Layer 7 load balancer or a reverse proxy

## Implementing Strangler Pattern With A Microservice, Behind An API Gateway Pattern, Behind A Request Reuter
* Sometimes it's not as easy as just reuting a request and than the recommend way is to implement a Microservice (greenfield) behind a API Gateway pattern
* The API Gateway pattern should in turn be behind a Request Reuter to help with future strangulations

## How to access data from the legacy system by the new service
* Try to avoid the need for accessing/providing data between the new and the old
  * When it's necessary, Invoke a remote API provided by the legacy systems facade

## Further Reading
* [DDD Surrounded by Legacy Software](http://domainlanguage.com/ddd/surrounded-by-legacy-software/)
* [Refactoring a Monolith into Microservices](https://www.nginx.com/blog/refactoring-a-monolith-into-microservices/)
* [Strangler Applications](http://paulhammant.com/2013/07/14/legacy-application-strangulation-case-studies/)
* [API Management](https://azure.microsoft.com/en-us/services/api-management/)
