<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#introduction">Introduction</a>
      <ol>
        <li><a href="#course-target">Course Target</a></li>
        <li><a href="#use-cases---e-commerce-domain">Use Cases - E-Commerce Domain</a></li>
      </ol>
    </li>
    <li><a href="#monolithic-architecture">Monolithic Architecture</a>
      <ol>
        <li><a href="#scalability">Scalability</a></li>
        <li><a href="#deployments">Deployments</a></li>
      </ol>
    </li>
    <li><a href="#layered-n-layer-architecture">Layered (N-Layer) Architecture</a>
</details>

&nbsp;

## About The Project

- Design Microservices Architecture with Patterns & Principles
- Handle millions of request with designing high scalable and high available systems on microservices architecture.
- [Mehmet Ozkaya](https://github.com/mehmetozkaya)

&nbsp;

## Introduction

- [Medium - Monolithic to Microservices Architecture with Patterns & Best Practices](https://medium.com/design-microservices-architecture-with-patterns/monolithic-to-microservices-architecture-with-patterns-best-practices-a768272797b2)

![design-journey](/diagrams/design-journey.png)

### Course Target

- Hands-on Design Activities
- Iterate Design Architecture from On-Premises to Cloud Serverless
- Evolves architecture Monolithic to Event-driven Microservices
- Refactoring System Design for handling million of requests
- Apply best practices with mcroservices design patterns and principles
- Examine microservices patterns with all aspects like Communications, Data Management, Caching and Deployments
- Prepare for Software Architecture Interviews
- Prepare for System Design Architecture Interview exams

&nbsp;

![journey1](/diagrams/journey1.png)

- <b>Subcomponents of Architectures</b>
  - MS Communications (Sync/ Async)
  - MS Data Management (Database/ Query/ Commands)
  - MS Design Patterns & Principles
  - MS Caching
  - MS Deployment

![journey2](/diagrams/journey2.png)

- <b>Evolve Architecture</b>
  - How can we scale the application?
  - How many request that we need to handle in our application?
  - How many second Latency is acceptable for our arch?

### Use Cases - E-Commerce Domain

- Functional Requirements
  - List products
  - Filter products as per brand and categories
  - Put products into the shopping cart
  - Apply coupon for discounts and see the total cost all for all of the items in shopping cart
  - Checkout the shopping cart and create an order
  - List my old orders and order items history
- User Stories
  - As a user I want to list products
  - As a user I want to filter products as per brand and categories
  - As a user I want to put products into the shopping cart so that I can check out quickly later
  - As a user I want to apply coupon for discounts and see the total cost all for all of the items that are in my cart
  - As a user I want to checkout the shopping cart and create an order
  - As a user I want to list my old orders and order items history
  - As a user I want to login the system as a user and the system should remember my shopping cart items
- Non-Functional Requirements
  - Scalability
  - Availability
  - Reliability
  - Maintability
  - Usability
  - Eficiency
- Request per Second and Acceptable Latency

| Concurrent Users | Requests/second | Latency (Expected) |
| :--------------: | :-------------: | :----------------: |
|        2K        |      0.5K       |                    |
|       20K        |       12K       |                    |
|       100K       |       80K       |      <= 2 Sec      |
|       500K       |      300K       |         ?          |

&nbsp;

---

&nbsp;

## Monolithic Architecture

- User Interface -> Business Logic -> Data Access -> DB
- Challenges
  - Single codebase
  - Big deployment
    - Complicated to understanding
  - Single jar/war file
  - Difficult to manage
    - Making New changes
    - Scalability
  - Hard to implement new features
    - New technology barriers
- Benefits for small application
  - Build (Simple to develop)
  - Test (Easier debugging and testing)
  - Simple to Deploy
  - Troubleshoot
  - Scale vertically (scale up)

![monolithic_architecture](/diagrams/monolithic_architecture.png)

- Simply to:
  - develop
  - deploy
  - scale

![reference_architecture1](/diagrams/reference_architecture1.png)

&nbsp;

![reference_architecture2](/diagrams/reference_architecture2.png)

&nbsp;

![reference_architecture3](/diagrams/reference_architecture3.png)

- Design principles
  - <b>DRY:</b> Don’t Repeat Yourself
  - <b>KISS:</b> Keep It Simple, Stupid
  - <b>YAGNI:</b> You Ain’t Gonna Need It
- Communication
  - Inter-Process Communication (Transaction Management)
    - Single database of the whole application
    - Simply commit and rollback operations

```
function place_order()
  do_payment
  decrease_stock
  send_shipment
  generate_bill
  update_order
```

- Same server with all modules
- Processes to communicate with each other by method calls into the code

### Scalability

- [Webairy - horizontal and vertical scaling](https://www.webairy.com/horizontal-and-vertical-scaling/)
- The number of requests an application can handle
- To prevent downtime, and reduce latency, you must scale
- <b>Vertical Scaling</b>
  - Vertical scaling by adding more power
  - Makes the nodes stronger
  - Adding more computing power
  - Same code on machines with better specs
  - Adding additional CPU, RAM, and DISK
  - Increase power since to hardware limitations when you reach the maximum capacity
- <b>Horizontal scaling</b>
  - Horizontal scaling by adding more machines
  - Splitting the load between different servers
  - Adds more instances of machines
  - Share the processing power
  - Gives you scalability but also reliability
  - Stateful or Stateless
  - CAP Theorem

![horizontal_and_vertical_scaling](/diagrams/horizontal_and_vertical_scaling.jpg)

- Load Balancer
  - Balance the traffic
  - Spread the traffic across a cluster
  - Consistent hashing algorithms

### Deployments

- Single code base
- Affects the whole system
- Not reliable
- Expensive and risky

![deployments_for_monolithic_architecture](/diagrams/deployments_for_monolithic_architecture.png)

&nbsp;

---

&nbsp;

## Layered (N-Layer) Architecture

- [Medium - Layered (N-Layer) Architecture](https://medium.com/design-microservices-architecture-with-patterns/layered-n-layer-architecture-e15ffdb7fa42)
- Presentation tier, for example, a web app.
- Business tier, including use case implementations
- A data tier, such as a SQL database.

![layered_architecture](diagrams/layered_architecture.png)

- Design principles
  - <b>Separation of Concerns (SoC)</b>
    - Elements in the software should be unique
    - Separate responsibilities
    - Limits to allocate Responsibilities
    - Low-coupling, high-cohesion
  - [<b>SOLID</b>](https://medium.com/bgl-tech/what-are-the-solid-design-principles-c61feff33685)
    - Single Responsibility Principle
    - Open-Closed Principle
    - Liskov Substitution Principle
    - Interface Segregation Principle
    - Dependency Inversion Principle

&nbsp;

---

&nbsp;
