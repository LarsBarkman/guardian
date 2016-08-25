# Containerized Microservices Architecture

## Context

### Microservices Architecture
>In short, the microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API. These services are built around business capabilities and independently deployable by fully automated deployment machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies.

> -- James Lewis and Martin Fowler

Source: [Microservices Resource Guide](http://martinfowler.com/microservices/#what)

#### A Comprehensive Presentation of Microservice Architectures, Presented by [Neal Ford](http://nealford.com/)
[![Building Microservice Architectures](http://img.youtube.com/vi/pjN7CaGPFB4/0.jpg)](https://www.youtube.com/watch?v=pjN7CaGPFB4)

### Containerized
> Containers are a solution to the problem of how to get software to run reliably when moved from one computing environment to another. This could be from a developer's laptop to a test environment, from a staging environment into production and perhaps from a physical machine in a data center to a virtual machine in a private or public cloud.

> Put simply, a container consists of an entire runtime environment: an application, plus all its dependencies, libraries and other binaries, and configuration files needed to run it, bundled into one package. By containerizing the application platform and its dependencies, differences in OS distributions and underlying infrastructure are abstracted away.

Source: [What are containers and why do you need them?](http://www.cio.com/article/2924995/enterprise-software/what-are-containers-and-why-do-you-need-them.html)

## Motivation behind the choice
* Microservices offer the flexibility that is needed for Continuous Improvement

## Alternatives that could have been chosen, but was not
* Service-based Architecture instead of Microservices
* Virtual Machines instead of Containers

## Further Reading
* [Microservices Resource Guide](http://martinfowler.com/microservices/)
* [What are containers and why do you need them?](http://www.cio.com/article/2924995/enterprise-software/what-are-containers-and-why-do-you-need-them.html)
