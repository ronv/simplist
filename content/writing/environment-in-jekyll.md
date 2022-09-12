---
comments: true
date: "2019-10-27T00:00:00Z"
description: Use liquid variable to separate production from development
summary: Use liquid variable to separate production from development.
categories:
- article
tags:
- jekyll
title: Environments in Jekyll
---

Jekyll is a simple, blog-aware, static site generator perfect for personal, project, or organization sites. Jekyll takes your content, renders Markdown and Liquid templates, and spits out a complete, static website ready to be served by Apache, Nginx or another web server.

In the ```build``` (or ```serve```) arguments, you can specify a Jekyll environment and value. The build will then apply this value in any conditional statements in your content. For example, if you need to separate production from development (for example comments), you can use liquid variable ```jekyll.environment``` which can be exported or used inline with ```JEKYLL_ENV=development jekyll serve --watch```.

Example:
```
{% if jekyll.environment == "production" %}
  <script>
    // JavaScript snippet...
  </script>
{% endif %}

```

When you build your Jekyll site, the content inside the ```if``` statement won’t be run unless you also specify a ```production``` environment in the build command.