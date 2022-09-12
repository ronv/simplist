---
date: "2018-11-12T00:00:00Z"
description: How to set a custom CSS or JS for each page
summary: How to set a custom CSS or JS for each page.
categories:
- article
tags:
- jekyll
title: Page specific assets in Jekyll
---

If you want to be able to add specific CSS or JS to specific pages of the website use a front matter variable to define which style is applied for a specific page.

Here is YAML:

```yaml
---
css: costum.min
js: jquery.min
---
``` 

And template for ```<head>``` section of each page:

```yaml
{% if page.css %}
  {% for stylesheet in page.css %}
  <link rel="stylesheet" href="{{ site.baseurl }}/assets/css/{{ stylesheet }}.css" type="text/css">
  {% endfor %}
{% endif %}
{% if page.js %}
  {% for js_file in page.js %}
  <script src='{{ site.baseurl }}/assets/js/{{ js_file }}.js' type="text/javascript"></script>
  {% endfor %}
{% endif %}
```