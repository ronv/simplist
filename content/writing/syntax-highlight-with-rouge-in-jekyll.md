---
comments: true
date: "2018-12-23T00:00:00Z"
description: Enable syntax highlighting in your site
summary: Enable syntax highlighting in your site.
categories:
- article
tags:
- jekyll
title: Syntax highlight with Rouge in Jekyll
---

Rouge is a popular syntax highlighter written in Ruby to provide the capability of syntax highlighting for code written on html pages. By default, Jekyll 3 and above versions comes with Rouge. It can highlight 100 different languages, and output HTML or ANSI 256-color text. Its HTML output is compatible with stylesheets designed for pygments.

To get syntax highlighting working in Jekyll, we need to enable the Rouge syntax highlighter. Open the ```_config.yml``` file and add the following line:

```yaml
highlighter: rouge
```

If you’re still using Jekyll 2, then open your terminal and enter the following command:

```bash
gem install rouge
```

Rouge is compatible with the Pygments syntax highlighter, which means that we can use themes created for Pygments. You can preview themes [here](https://w3techs.com/). Once you found your favourite theme, view the page source to find it and copy or save it to your site css file.

Pygments themes uses ```.syntax``` as the default class, so you will need to replace the ```.syntax``` with ```.highlight``` class in the ```pygments.css``` file or change the default ```.highlight``` css class name to ```.syntax``` in the Jekyll’s ```_config.xml``` file like this:

```yaml
markdown: kramdown
highlighter: rouge
kramdown:
  input: GFM
  syntax_highlighter_opts:
    default_lang: html
    css_class   : 'syntax'
```



