---
date: "2017-01-03T00:00:00Z"
description: Using data folder to build Jekyll navigation
summary: Using data folder to build Jekyll navigation.
categories:
- article
tags:
- jekyll
title: Creating navigation menu in Jekyll
---

In your ```_data``` folder add a new navigation (```navigation.yml```) file:

```yaml
- title: "Home"
  href: "/"

- title: "About"
  href: "/about/"

- title: "Projects"
  subcategories:
    - subtitle: "Project1"
      subhref: "#"
    - subtitle: "Project2"
      subhref: "#"
```

In your ```_includes``` folder add a new navigation (```navigation.html```) file:

```html
<nav>
  <ul>
    {% for nav in site.data.nav %}
      {% if nav.subcategories != null %}
        <li>
          <a href="{{ site.url }}{{ nav.url }}">{{ nav.title }} ▼</a>
          <ul>
          {% for subcategory in nav.subcategories %}
            <li><a href="{{ site.url }}{{ subcategory.subhref }}">{{ subcategory.subtitle }}</a></li>
          {% endfor %}
          </ul>
        </li>
      {% elsif nav.title == page.title %}
         <li class="active">
           <a href="{{ nav.url }}">{{ nav.title }}</a>
         </li>
      {% else %} 
        <li>
          <a href="{{ site.url }}{{ nav.href }}">{{ nav.title }}</a>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
</nav>
```