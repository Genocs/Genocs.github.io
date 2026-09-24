From idea to software
===

This site is a working map of how a product idea becomes a shippable system. Delivery is rarely linear. Constraints surface late, objectives move, and unexamined change quietly taxes the whole architecture.

Building software at a professional standard requires depth across product, architecture, operations, and engineering — and a discipline about what *not* to build.

## Golden rules

Two constraints that scale better than process:

- **DRY** — Don't Repeat Yourself
- **KISS** — Keep It Simple

DRY is about a single source of truth: logic and data live in one place, then get reused through well-chosen abstractions. Duplication is not only extra typing; it is extra failure modes.

KISS is about resisting accidental complexity. Prefer the smallest design that meets the requirement. Complexity that is not earned by the problem becomes the tax you pay in review, operations, and every subsequent change.

Before any work starts:

> The cheapest implementation is the one you do not write.  
> Ask first: **is this required?**

## Shape the idea

Stakeholders must make the product explicit. Competitive context, **MVP** (minimum viable product), and **KPIs** (key performance indicators) belong here — before engineering commits to a shape that is expensive to reverse.

*What* and *why* are insufficient without *how*:

- **What** is being built
- **Why** it exists
- **How** it will be delivered

Omit any of the three and the program drifts: scope without a market, purpose without a design, or a design without a reason.

### MVP

The MVP is the smallest product that can be placed in front of real users. It is a learning instrument, not a reduced wish list. Protect the invariants that define the product; everything else is optional until evidence says otherwise.

### KPIs

KPIs are the compass. They tell you where the business actually is, and whether the original plan still deserves the next increment of investment.

> At this stage the engineering team stays out of the critical path, except where a technical conversation is needed to keep the community warm.

## Project management

Tooling is secondary to cadence and visibility. These are the systems I have used in practice:

- [Jira](https://www.atlassian.com/software/jira)
- [Trello](https://trello.com/)
- [Figma](https://www.figma.com/)
- [Azure DevOps](https://dev.azure.com/)
- Microsoft Project

## Product architecture

Architecture is constraint-driven. Cloud is the default for many organisations; on-premises remains non-negotiable in others. Neither is a style — each is a set of operational and regulatory facts.

Enterprise-grade systems tend to rest on:

- Clean Architecture (clear boundaries, dependency direction, testable cores)
- Microservice architecture (independently deployable capabilities, explicit contracts)

Choose the grain of distribution for the organisation you have, not the one described in a conference talk.

## DevOps

### Source control

Version control is the system of record for the work. It is required for a team of one as much as for a platform organisation. Hosting may be public or private:

- [Bitbucket](https://bitbucket.org/)
- [GitHub](https://github.com/)
- [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/)

### CI/CD

Build, test, and promote artifacts on a pipeline you trust:

- [CircleCI](https://circleci.com/)
- [Travis CI](https://travis-ci.com/)
- [Azure DevOps](https://dev.azure.com/)

### Package and artifact stores

- [NuGet](https://www.nuget.org/) — .NET
- [MyGet](https://www.myget.org/) — .NET
- [Docker Hub](https://hub.docker.com/) — container registry
- Private registries, when the artifact cannot leave the estate

## Runtime platforms

Where the solution actually runs:

- Local — standalone applications
- Device — mobile and embedded
- On-premises
- Public cloud
  - [Azure](https://portal.azure.com/)
  - [AWS](https://aws.amazon.com/)
  - [Google Cloud](https://cloud.google.com/)
  - [DigitalOcean](https://cloud.digitalocean.com/)

### Supporting infrastructure

**Data stores**

- [MongoDB](https://www.mongodb.com/)
- [Elasticsearch](https://www.elastic.co/)
- [Firebase Realtime Database](https://firebase.google.com/products/realtime-database)
- [Neo4j](https://neo4j.com/)
- [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server)
- [Oracle Database](https://www.oracle.com/database/)

**Messaging**

- [RabbitMQ](https://www.rabbitmq.com/)

**Service bus / messaging frameworks**

- [NServiceBus](https://particular.net/)
- [MassTransit](https://masstransit.io/)
- [Rebus](https://github.com/rebus-org/Rebus/)
- [RawRabbit](https://github.com/pardahlman/RawRabbit/)

**Outbound channels**

- Email
- SMS
- Push and in-app notification

## Software delivery

The implementation surface typically includes:

- Backend services
- Frontend applications
- Mobile and embedded
- Machine learning
- Data analysis and processing

### Languages

- C / C++
- C# / .NET
- HTML / CSS
- Kotlin
- Go
- Python
- Node.js
- Java

## Notes
{: #notes}

Field notes on architecture, tooling, and delivery.

<ul class="notes-index">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.date | date: "%Y-%m-%d" }} — {{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
