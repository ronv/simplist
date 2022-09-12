---
date: "2018-05-13T00:00:00Z"
description: A Liquid tag for Jekyll sites that allows embedding Gists
summary: A Liquid tag for Jekyll sites that allows embedding Gists.
categories:
- article
tags:
- jekyll
title: Displaying GitHub Gists in Jekyll sites
---

Add this line to your application's Gemfile:

    $ gem 'jekyll-gist'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install jekyll-gist

Then add the following to your site's `_config.yml`:

```
plugins:
  - jekyll-gist
```

If you are using a Jekyll version less than 3.5.0, use the `gems` key instead of `plugins`. Use the tag as follows in your Jekyll pages, posts and collections by adding ```{% gist id %}```.