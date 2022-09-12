---
date: "2018-02-03T00:00:00Z"
description: Using an image caption in Jekyll
summary: Using an image caption in Jekyll.
categories:
- article
tags:
- jekyll
title: Image caption in Jekyll
---

If you don't want to use any plugins (which means you can push it to GitHub directly without generating the site first), you can create a new file named <code>image.html</code> in <code>_includes</code>:

```html
<figure class="image">
  <img src="{{ include.url }}" alt="{{ include.description }}">
  <figcaption>{{ include.description }}</figcaption>
</figure>
```

Display the image from your markdown with:

```
{% include image.html url="/images/bird.jpg" description="Bird" %}
```


