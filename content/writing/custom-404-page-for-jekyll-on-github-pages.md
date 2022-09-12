---
date: "2017-11-15T00:00:00Z"
description: Serve custom 404 error pages with Jekyll
summary: Serve custom 404 error pages with Jekyll.
categories:
- article
tags:
- jekyll
title: Custom 404 page for Jekyll on Github pages
---

You can easily serve custom 404 error pages with Jekyll to replace the default 404 error page when people try to access nonexistent pages on your site. Any ```404.html``` at the root of your ```_site``` directory will be served automatically by GitHub pages and the local development server. Simply add a ```404.md``` or ```404.html``` at the root of your site’s source and include front matter data to use the theme’s base layout like this:

```yaml
---
layout: page
title: 404
---
```

Or if you plan to organize your files under subdirectories, the error page should have the following front matter data, set: ```permalink: /404.html```.

Example:
```
---
layout: default
permalink: /404.html
---

# 404

Page not found!
```