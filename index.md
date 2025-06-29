Welcome to Genocs - GitHub pages
===

This repo is intended to recap the main steps required to convert an idea into a software product. 

This process it is not straightforward ever. There are a lot of variables and these variables, often, are not clear at the beginning. Besides that, aims and targets could change during the ‘path’. Often this happens without evaluating the impact of the changes on the entire ecosystem.

To design a product and to implement it correctly, as software project it is necessary to have a clear and deeply knowledge of different areas, technologies, tools, and foremost, the right mindset.


## Golden Rules
Before starting to do anything, don't forget to apply these general purpose golden rules!

- DRY (Don't repeat yourself)
- KISS (Keep It Simple Stupid)


**Don't Repeat Yourself** (DRY) is a software development principle that states that software developers should avoid repeating the same code or data in multiple places. This principle encourages developers to create abstractions and modularize their code, making it easier to maintain and update. By following the DRY principle, developers can reduce the amount of time spent on debugging and refactoring code, as well as improve the overall quality of their software.

The **Keep It Simple Stupid** (KISS) pattern is a software development principle that encourages developers to create solutions that are easy to understand and maintain. This pattern emphasizes the importance of writing code that is straightforward, efficient, and free of unnecessary complexity. By following this pattern, developers can create applications that are easier to debug and maintain over time.


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

Miss one of these key points and the solution will fail miserably.

### MPV
Defining the MVP target is needed to be fast delivery something to the market. This is important to have feedback as well as to keep in mind what are the core concept that canno be disattended. 

### KPI
The KPI definition allow to have a monitor, ***the compass*** to estimate where the business is, and to apply the right corrections on the original plan.

> ### NOTE
> - During this stage the technical team is not involved ***(unless to warm-up the tech community) ***



## Project Management
There are a lot of different tools out there. 

Some of them that I used, and I was comfortable with. A short list below:   
- [[Atlassian] Jira](https://www.atlassian.com/software/jira)
- [[Atlassian] Trello](https://trello.com/)
- [Figma](https://www.figma.com/)
- [[Microsoft] VSTS](https://dev.azure.com/)
- Microsoft Project


## Product Architecture
Design the architecture is not a simple task. 

Different companies have different constraints. 

For most of them be on the cloud is a must. It couldn’t be otherwise. But there are contexts where On-Prem is an unassailable requirement.

An entreprise grade software solution is 

- Clean Architecture patterns
- Microservice Architecture


## DevOps

### Source code Versioning
The source code versioning is the repository where different developers store the result of their work. This tool could and should be used even when the development team is composed by few members even only one.

These repositories allow to store projects both in a public and private fashion. The most important one is: 
- [[Atlassian] Bitbutchet](https://bitbucket.org/)
- [GitHub](https://github.com/)
- [[Microsoft] VSTS](https://azure.microsoft.com/en-us/services/devops/)

### CI/CD (Continuous Integration / Continuous Deploy) (How to build tests and run)
- [Circle CI](https://circleci.com/)
- [Travis CI](https://travis-ci.com/)
- [[Microsoft] Azure Devops](https://dev.azure.com/)

### Package manager (How store the artifacts)
- [NuGet](https://www.nuget.org/) [.NET]
- [MyGet](https://www.myget.org/) [.NET]
- [DockerHub](https://hub.docker.com/) [Container registry]
- Private Repository


## The platforms (Where the solution is executed)

- Local [StandAlone local Application]
- Device [Mobile and/or Embedded Application]
- On-Prem
- Public Cloud
	- [Azure](https://portal.azure.com/)
	- [AWS](https://aws.amazon.com/)
	- [Google Cloud](https://cloud.google.com/)
	- [Digital Ocean](https://cloud.digitalocean.com/)

### The external services (What kind of infrastructure the services are needs)

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
- Machine learning 
- Data analysis and processing

### Backend services

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
