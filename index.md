---
title: "Welcome to Genocs"
---

The Idea
===

This site is hosted on Github and built with Github pages.

The main scope of documentation is to recap what I learned from participating to the development of many different project during years.
Each project provides a lot of insight coming both from both positive and negative side.

Starting from that I decided to describe some of the main topic required to convert an idea into a software product.

### How Design Implement and Delivery a software product
This process is not straightforward ever. There are a lot of variables and these variables, often, are not clear at the beginning. Besides that, aims and targets change during the ***path***, and this happens without evaluating the impact of the changes on the entire ecosystem.

To design a product and implement it as software project it is necessary to have a clear and deeply knowledge of different areas. Interdisciplinary skills are required. It is required mastering Technologies, Tools, people and foremost: **the right mindset**.

## Golden Rules
Before starting to do anything, do not forget to apply these general golden rules!

- DRY (Don't repeat yourself)
- KISS (Keep It Simple Stupid)

and remember:

> - The best and fastest way to do something is don't.
> - So before start doing something, ask yourself: **it is really needed**?


## Setup the Idea
In this stage, the stakeholders should describe the idea behind the product. 

The market analysis like competitors evaluation, **MVP** (Minimum Viable Product) and the **KPI** (Key Product Indicators) identification should be defined upfront and deeply evaluated.

Terms like ***what*** and ***why*** are not enough. The ***how*** is very important as well.

- **What** we are going to build
- **Why** we are doing that
- **How** we are building the solution

Just missing one of these key points and the solution will fail miserably.

### MPV
The MVP definition is needed to deliver something valuable to the market quickly. This is important to have concrete feedback as well as to reevaluate the core concepts. Sometime the original idea needs to be revisited a lot of time before receiving positive feedback from the market.  

### KPI
The KPI definition allows to have a monitor. The KPI will be ***the compass*** to estimate where the project is and based on that to apply the right corrections. 

### Stakeholdes - Key Reference Persons

Following the early-stage attendants:
- Product Sponsor
- Product Owner
- Product Manager
- Solution Architect

## Project Management
There are a lot of different tools out there. 

Some of them are broadly adopted. Some of them are the standard ***de facto***. A brief list below:
- Microsoft Project
- [[Microsoft] VSTS](https://dev.azure.com/) 
- [[Atlassian] Jira](https://www.atlassian.com/software/jira)
- [[Atlassian] Trello](https://trello.com/)
- [Figma](https://www.figma.com/)


## Product Architecture
Designing the architecture is not a simple task. 

Different companies have different constraints. 

For most of them being on the **Cloud** is necessary. It couldn’t be otherwise. 

But there are contexts where **On-Prem** solution is an unassailable requirement.

An enterprise grade software solution is like a living organism. It changes over time, and this has a deep impact on the company shape as well. Both in terms of Processes, Tools, and Requirements.

A Startup is different from an ongoing company, and they are different from elderly companies.

> Pay attention: all of them could be valuable ones economically speaking. The management is completely different. 

- Clean Architecture patterns
- Microservice Architecture


## DevOps

### Source Code Versioning
The source code versioning is the repository where different developers store the result of their work. This tool could and should be used even when the development team is composed of few members, even only one.

These repositories allow us to store projects both in a public and private fashion. The most important ones are: 
- [[Atlassian] Bitbutchet](https://bitbucket.org/)
- [GitHub](https://github.com/)
- [Microsoft-VSTS](https://azure.microsoft.com/en-us/services/devops/)

### CI/CD (Continuous Integration / Continuous Deploy)
The CI/CD allows to define: How to run builds and tests software
- [Circle CI](https://circleci.com/)
- [GitHub Action](https://github.com/features/actions/)
- [Travis CI](https://travis-ci.com/)
- [Microsoft-Azure Devops](https://dev.azure.com/)


### Package manager
The Package Manage allows to handle: Where to store the artifacts
- [NuGet](https://www.nuget.org/) [.NET]
- [MyGet](https://www.myget.org/) [.NET]
- [DockerHub](https://hub.docker.com/) [Container registry]
- Private Repository


### The Host 
Where the compiled is executed

- Local [StandAlone Local Application]
- Device [Mobile and/or Embedded Application]
- On-Prem
- Public Cloud
	- [Azure](https://portal.azure.com/)
	- [AWS](https://aws.amazon.com/)
	- [Google Cloud](https://cloud.google.com/)
	- [Digital Ocean](https://cloud.digitalocean.com/)

### The external services
What kind of infrastructure the services are needs

- Datastore
    - [MongoDB](https://www.mongodb.com/)
    - [Elastic Search](https://www.elastic.co/)
    - [Google Firebase Database](https://firebase.google.com/products/realtime-database)
    - [Neo4j](https://neo4j.com/)
    - [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server)
    - [Oracle database](https://www.oracle.com/database/) 
	
- Enterprice message broker
    - [RabbitMQ](https://www.rabbitmq.com/)

- Enterprice Service Bus
	- [Particular-NServicebus](https://particular.net/)
	- [MassTransit](https://masstransit-project.com/)
	- [Rebus](https://github.com/rebus-org/Rebus/)
	- [RawRabbit](https://github.com/pardahlman/RawRabbit/)


- Mail sender
- SMS sender
- Notification services

## Software development

- Backend services
- Frontend Services
- Mobile and Embedded
- Machine learning modules
- Data analysis and processing

## Programming languages
- C/C++
- .NET C#
- html/css
- kotlin
- GO
- Python
- nodejs
- Java

### Backend services


### Post
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
