---
date: "2018-06-07T00:00:00Z"
description: How to apply the active class for the current page in Jekyll
summary: How to apply the active class for the current page in Jekyll.
categories:
- article
tags:
- jekyll
title: Applying the active class for the current page in Jekyll
---


Create a data file ```navigation.yml``` file and write your nav text and urls within a folder ```_data ```.

```yaml
- text: About
  url: /about/

- text: Projects
  url: /projects/

- text: Work
  url: /work/
```

In your page you're going to create a loop through your data menu list from yaml file and add an active class if the current page’s url matches the link.

```
{% for nav in site.data.navigation %}
<li{% if navigation.url == page.url %} class="active"{% endif %}><a href="{{ navigation.url }}">{{ navigation.text }}</a></li>
{% endfor %}
```

Add CSS for active class.

```css
li.active a {
    color: lightgray;
    cursor: default;
  }
```

To make sure the ```navigation.url``` (stored in the YAML file) matches the ```page.url```, it can be helpful to print the ```{{ page.url }}``` to the page.