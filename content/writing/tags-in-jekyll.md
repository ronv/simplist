---
comments: true
date: "2019-11-01T00:00:00Z"
description: Adding tags to a Jekyll powered website
published: true
summary: Adding tags to a Jekyll powered website.
categories:
- article
tags:
- jekyll
title: Tags in Jekyll
---

Here is a solution how to generate pages for each tag that will list all posts for a tag. To assign tags to a post, just put their names, space separated (or as a YAML array if you prefer this way), in the front matter:
```
---
layout: post
title: Tags in Jekyll
description: Adding tags to a Jekyll powered website
summary: Adding tags to a Jekyll powered website.
comments: true
tags: [tags, jekyll]
published: true
---
```

That sets up the post to have tags. To get the tags pulled onto a page, create two files: ```_layouts/tag.html``` and ```_plugins/tags.rb```. The ```_layouts/tag.html``` file is necessary for the ```_plugins/tags.rb``` script to actually run. Put the following plugin at ```_plugins/tags.rb```:
```
module Jekyll
  class TagPageGenerator < Generator
    safe true

    def generate(site)
      tags = site.posts.docs.flat_map { |post| post.data['tags'] || [] }.to_set
      tags.each do |tag|
        site.pages << TagPage.new(site, site.source, tag)
      end
    end
  end

  class TagPage < Page
    def initialize(site, base, tag)
      @site = site
      @base = base
      @dir  = File.join('tag', tag)
      @name = 'index.html'

      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag.html')
      self.data['tag'] = tag
      self.data['title'] = "Tag: #{tag}"
    end
  end
end
```

This script creates a directory (folder) for each tag in your blog, and creates an ```index.html``` file in it and in that ```index.html file``` tag template.

In the ```_layouts/tag.html``` file, put this:
```
---
layout: default
---

<h1>{{page.tag}}</h1>
<ul>
  {% for post in site.posts %}
  {% if post.tags contains page.tag %}
  <li><a class="post" href="{{ post.url }}">{{ post.title }}</a></li>
  {% endif %}
  {% endfor %}
</ul>
```

At the end of each post add the following:
```
<p>
  Tagged 
  {% for tag in page.tags %}
  <a class="post" href="/tag/{{tag}}">#{{tag}}</a>{% unless forloop.last %}, {% endunless %}
  {% endfor %}
</p>
```

That's it!
