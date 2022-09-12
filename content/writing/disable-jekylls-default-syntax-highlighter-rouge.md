---
date: "2018-02-05T00:00:00Z"
description: How to disable Jekyll's default syntax highlighter
summary: How to disable Jekyll's default syntax highlighter.
categories:
- article
tags:
- jekyll
title: Disable Jekyll's default syntax highlighter Rouge
---

By default Jekyll have Rouge syntax highlighter. In some cases, you may want to disable it. To get Rouge disabled in Jekyll, just do the following.

- Open the ```_config.yml``` file located at the root directory.
- Add the following line:

```yaml
highlighter: none
```

- To disable Rouge on website which are hosted on Github Pages add the following line:

```yaml
markdown: kramdown
kramdown:
   syntax_highlighter_opts:
      disable : true
```