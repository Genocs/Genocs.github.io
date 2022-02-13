---
title: "Genocs"
---

This is the Genocs entrypoint repo 

# Post
<ul>
  {% for post in site.posts %}
    <li>
      <a href="/Genocs.github.io{{ post.url }}">{{ post.title }}</a>
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

# picoservices
This folder contains the template to build webApi with different languages.

Supported languages are:
- golang
- .NET
- python
- nodejs


## Microservice Patterns

| Item                | .NET                                                  | Github                                                        |
| :------------------ | ----------------------------------------------------: | ------------------------------------------------------------: |
| devmentors          | [devmentors](https://devmentors.io/)                  |  [devmentors](https://github.com/devmentors)[snatch-dev](https://github.com/snatch-dev)     |

## Clean Architecture

| Item                | .NET                                                  | Github                                                        |
| :------------------ | ----------------------------------------------------: | ------------------------------------------------------------: |
| devmentors          | [devmentors](https://devmentors.io/)                  |  [devmentors](https://github.com/devmentors)[snatch-dev](https://github.com/snatch-dev)     |
| paulovich           | [paulovich](https://paulovich.net/clean-architecture-for-net-applications/)                  |  [manga](https://github.com/ivanpaulovich/clean-architecture-manga)[caju](https://github.com/ivanpaulovich/dotnet-new-caju)     |



## IA and Machine Learning

| Item                | .NET                                                  | Github                                                        |
| :------------------ | ----------------------------------------------------: | ------------------------------------------------------------: |
| aforgenet           | [aforgenet](http://www.aforgenet.com/)                |  [aforgenet](https://github.com/andrewkirillov/AForge.NET)    |
| accord-framework    | [accord-framework](http://accord-framework.net/)      |  [accord-framework](https://github.com/accord-net/framework)  |
