# Architecture

defining software designs through design docs.
The design doc documents the high level implementation strategy and key design decisions with emphasis on the trade-offs that were considered during those decisions.

As software engineers our job is not to produce code per se, but rather to solve problems

design docs fulfill the following functions in the software development lifecycle:

Early identification of design issues when making changes is still cheap.

Achieving consensus around a design in the organization.

Ensuring consideration of cross-cutting concerns.

Scaling knowledge of senior engineers into the organization.

Form the basis of an organizational memory around design decisions.

Acts as a summary artifact in the technical portfolio of the software designer(s).

Context and scope #

This section gives the reader a very rough overview of the landscape in which the new system is being built and what is actually being built.

Goals and non-goals #
A short list of bullet points of what the goals of the system are, and, sometimes more importantly, what non-goals are.

A good example would be “ACID compliance”; when designing a database,

The actual design #
This section should start with an overview and then go into details.

The design doc is the place to write down the trade-offs you made in designing your software. Focus on those trade-offs to produce a useful document with long-term value. That is, given the context (facts), goals and non-goals (requirements), the design doc is the place to suggest solutions and show why a particular solution best satisfies those goals.

System-context-diagram #
In many docs a system-context-diagram can be very useful. Such a diagram shows the system as part of the larger technical landscape and allows readers to contextualize the new design given its environment that they are already familiar with.

APIs #
If the system under design exposes an API, then sketching out that API is usually a good idea.

Alternatives considered #
This section lists alternative designs that would have reasonably achieved similar outcomes. The focus should be on the trade-offs that each respective design makes and how those trade-offs led to the decision to select the design that is the primary topic of the document.

Cross-cutting concerns #
This is where your organization can ensure that certain cross-cutting concerns such as security, privacy, and observability are always taken into consideration.

The design doc lifecycle #
The steps in the lifecycle of a design document are:
Creation and rapid iteration
Review (may be in multiple rounds)
Implementation and iteration
Maintenance and learning
When things have progressed sufficiently to have confidence that further reviews are unlikely to require major changes to the design, it is time to begin implementation.

Conclusions #
Design docs are a great way to gain clarity and achieve consensus around solving the hardest problems in a software project
the hexagonal architecture is an approach used to divide the application into inside and outside parts. They are connected through ports (exposed by the inside) and adapters (implemented by the outside). So, by applying this approach, the core use case code remains intact and can serve to multiple channels, supporting different protocols. It also helps to make the application tested easily. 


a confusion between event-driven and event-sourced architecture. In an event-driven architecture, components perform tasks in response to received events, and emit events to notify about changes in state. In event sourcing, state changes are recorded as events and the current state of an entity is calculated from all events related to the entity

If you’re not facing some kind of problem, you don’t need a new tool. Full stop.make sure that you’re choosing a technology because it solves real needs for you, not because the cool kids are doing it.https://www.simplethread.com/was-mongodb-ever-the-right-choice/


The hexagonal, or ports and adapters or onion architecture, solves these problems. In this architecture, the application in the inside communications over some number of ports with systems on the outside.


Break a monolith to microservices - 12 best practices & design principles to follow in 2020
Have separate data storages
Before you even consider the migration, figure out how you will segregate the data storage according to the various constituting microservices. This can be done by using the architecture pattern such as CQRS (Command and Query Responsibility Segregation) to make the data private to each of the microservices.

Build dedicated teams.it makes more sense to allocate dedicated teams for every microservice if you are planning to scale linearly and efficiently.


Use automation for independent deployment

Leverage the benefits of REST API
The REST (Representational State Transfer) APIs can work wonders for microservices as developers need not install any additional software or libraries while creating a REST API. At the same time, they provide a great deal of flexibility since the data is not tied to any particular method or resource.


Break down the migration into steps

Pair the right technology with the right microservice
If you are not sure which technology is best for your project, consider the following parameters during the decision-making process:

Maintainability
Fault-tolerance
Scalability
Cost of architecture
Ease of deployment
Consider Using Domain-Driven Design
Domain-Driven Design is nothing more than Object Oriented Programming applied to business models

Conclusion
Prior to initiating the process of transforming your system to microservices, it is crucial to have real reasons as to why you want to do it. Take the distinctive features of your system and work on changing one part of the system that hurts the most. Work on an incremental approach where you take out a not so critical part of the system and assess how it works which is also a great way of getting stakeholder buy-in and proceeding from there.

Native Multi-Threading
There are some challenges with multi-threading in general:

Using the resources optimally (CPU Cores / Memory)

Fine-tuning thread number and thread management
Lost control flow and context. The stack trace is bound to the thread not to the transaction so you will see only that small step assigned currently to the thread (debug, profile issues)
Synchronizing the execution
Debugging and Testing

* Logging
* Monitoring
  *circuit breaker

# BUILD TOOLS:

Gradle Buck (https://buck.build/setup/getting_started.html)
Pants https://www.pantsbuild.org/ (For python)

# DATABASES:

. RocksDB is a key-value store for running mission-critical workloads. It is optimized for fast, low latency storage.`

Maintaining goodwill is key to adoption. So if you have any unavoidable outages, communicate them and perhaps adapt your plans to reduce impact on your users. If something goes wrong and you have an outage (hint: you will) then apology and transparency will reassure them
Out-of-hours support, alerting systems and blameless incident retrospectives should be a priority
fundamentals of software infrastructure, like networking, scaling and disaster recovery. 

Infrastructure as Code:

Define everything as code
Continuously test and deliver all work in progress
Build small, simple pieces that you can change independently

A digital platform is a foundation of self-service APIs, tools, services, knowledge and support which are arranged as a compelling internal product.

-- Evan Bottcher
to be modest in the scope of your ambition - at first.
when upgrade project
upgrade tools and dependcies
run on new.version
compile on new version

Feature toggles


Versioning an API allows us to support different functionality for the same resource.


Canary deployment
A canary deployment, also known as a blue/green, red/black, or purple/red deployment, is the idea of releasing a new version of an application and only allowing a small percentage of traffic to reach it.

docs Version and effective date
Breaking changes that consumers will have to handle
New features that can optionally be used but don’t require any updates by consumers
Fixes and changes to existing APIs that don’t require consumers to change anything
Deprecation notices that are planned for future work

Upgrade consumers first
A good best practice is to upgrade consumer applications first. This gives us a chance to handle new message formats before we actually start publishing them.

One of these is maintaining backwards compatibility between components.