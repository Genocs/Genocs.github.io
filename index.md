Welcome to Genocs - GitHub Pages
===

This repository is intended to recap the main steps required to convert an idea into a software product.

This process is never straightforward. There are many variables involved, and these variables are often not clear at the beginning. Additionally, aims and targets can change during the journey. This often happens without evaluating the impact of these changes on the entire ecosystem.

To design a product and implement it correctly as a software project, it is necessary to have clear and deep knowledge of different areas, technologies, tools, and most importantly, the right mindset.

## Golden Rules
Before starting to do anything, don't forget to apply these general-purpose golden rules!

- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple, Stupid)

**Don't Repeat Yourself** (DRY) is a software development principle that states that software developers should avoid repeating the same code or data in multiple places. This principle encourages developers to create abstractions and modularize their code, making it easier to maintain and update. By following the DRY principle, developers can reduce the amount of time spent on debugging and refactoring code, as well as improve the overall quality of their software.

The **Keep It Simple, Stupid** (KISS) pattern is a software development principle that encourages developers to create solutions that are easy to understand and maintain. This pattern emphasizes the importance of writing code that is straightforward, efficient, and free of unnecessary complexity. By following this pattern, developers can create applications that are easier to debug and maintain over time.

And remember:

> - The best and fastest way to do something is not to do it at all.
> - So before starting to do something, ask yourself: **Is it really needed?**

## Setting Up the Idea
In this stage, stakeholders should describe the idea behind the product.

Market analysis, including competitor evaluation, **MVP** (Minimum Viable Product) definition, and **KPI** (Key Performance Indicators) identification should be defined upfront and thoroughly evaluated.

Terms like ***what*** and ***why*** are not enough. The ***how*** is very important as well.

- **What** we are going to build
- **Why** we are doing that
- **How** we are building the solution

Missing any of these key points will cause the solution to fail miserably.

### MVP
Defining the MVP target is necessary for fast delivery of something to the market. This is important to gather feedback as well as to keep in mind what are the core concepts that cannot be disregarded.

### KPI
The KPI definition allows you to have a monitor, ***the compass***, to estimate where the business is and to apply the right corrections to the original plan.

> ### NOTE
> - During this stage, the technical team is not involved ***(unless to warm up the tech community)***

## Project Management
There are many different tools available.

Here are some that I have used and found comfortable with. A short list below:
- [[Atlassian] Jira](https://www.atlassian.com/software/jira)
- [[Atlassian] Trello](https://trello.com/)
- [Figma](https://www.figma.com/)
- [[Microsoft] VSTS](https://dev.azure.com/)
- Microsoft Project

## Product Architecture
Designing architecture is not a simple task.

Different companies have different constraints.

For most of them, being on the cloud is a must. It couldn't be otherwise. But there are contexts where On-Premises is an unassailable requirement.

An enterprise-grade software solution includes:

- Clean Architecture patterns
- Microservice Architecture

## DevOps

### Source Code Versioning
Source code versioning is the repository where different developers store the results of their work. This tool could and should be used even when the development team consists of few members or even just one.

These repositories allow you to store projects both publicly and privately. The most important ones are:
- [[Atlassian] Bitbucket](https://bitbucket.org/)
- [GitHub](https://github.com/)
- [[Microsoft] VSTS](https://azure.microsoft.com/en-us/services/devops/)

### CI/CD (Continuous Integration / Continuous Deployment) (How to build, test, and deploy)
- [Circle CI](https://circleci.com/)
- [Travis CI](https://travis-ci.com/)
- [[Microsoft] Azure DevOps](https://dev.azure.com/)

### Package Manager (How to store artifacts)
- [NuGet](https://www.nuget.org/) [.NET]
- [MyGet](https://www.myget.org/) [.NET]
- [DockerHub](https://hub.docker.com/) [Container registry]
- Private Repository

## The Platforms (Where the solution is executed)

- Local [Standalone local Application]
- Device [Mobile and/or Embedded Application]
- On-Premises
- Public Cloud
	- [Azure](https://portal.azure.com/)
	- [AWS](https://aws.amazon.com/)
	- [Google Cloud](https://cloud.google.com/)
	- [Digital Ocean](https://cloud.digitalocean.com/)

### External Services (What kind of infrastructure the services need)

- Datastore
    - [MongoDB](https://www.mongodb.com/)
    - [Elasticsearch](https://www.elastic.co/)
    - [Google Firebase Database](https://firebase.google.com/products/realtime-database)
    - [Neo4j](https://neo4j.com/)
    - [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server)
    - [Oracle Database](https://www.oracle.com/database/)
	
- Enterprise Message Broker
    - [RabbitMQ](https://www.rabbitmq.com/)

- Enterprise Service Bus
	- [Particular-NServiceBus](https://particular.net/)
	- [MassTransit](https://masstransit-project.com/)
	- [Rebus](https://github.com/rebus-org/Rebus/)
	- [RawRabbit](https://github.com/pardahlman/RawRabbit/)

- Mail Sender
- SMS Sender
- Notification Services

## Software Development

- Backend Services
- Frontend Services
- Mobile and Embedded
- Machine Learning
- Data Analysis and Processing

### Backend Services

## Programming Languages
- C/C++
- .NET C#
- HTML/CSS
- Kotlin
- Go
- Python
- Node.js
- Java

### Backend Services

### Posts
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

<div class="linked_post">
    {% for post in site.posts %}
        {% assign post_url = post.url | replace: "/", "" %}
        {% if post_url == include.url %}
            <div class="linked_post_div">
                <article class="post">
                    <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
                    <p style="color: #969494; margin: 10px 0px; font-size: 18px;">
                        {{ post.date | date: "%B %e, %Y" }}
                    </p>
                </article>
            </div>
        {% endif %}
    {% endfor %}
    <br>
</div>
