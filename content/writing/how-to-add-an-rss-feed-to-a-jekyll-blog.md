---
date: "2018-09-11T00:00:00Z"
description: Generate an Atom (RSS-like) feed of your Jekyll posts
summary: Generate an Atom (RSS-like) feed of your Jekyll posts.
categories:
- article
tags:
- jekyll
title: How to add an RSS feed to a Jekyll blog
---

Add this line to your site's Gemfile:

```ruby
gem 'jekyll-feed'
```

And then add this line to your site's `_config.yml`:

```yml
plugins:
  - jekyll-feed
```

If you are using Jekyll < 3.5.0 use the `gems` key instead of `plugins`. The plugin will automatically generate an Atom feed at `/feed.xml`.