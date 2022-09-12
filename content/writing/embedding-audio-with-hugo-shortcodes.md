---
comments: true
date: "2022-04-20T00:00:00Z"
description: Adding audio shortcode to Hugo
summary: Adding audio shortcode to Hugo
categories:
- article
tags:
- hugo
title: Embedding audio with Hugo shortcodes
---

Hugo provides the ability to easily create custom shortcodes to meet your website’s needs. All you need to do is add an html file in the shortcodes folder with the html you want to render. 

To make a custom audio shortcode create an html file in the following location: `layouts/shortcodes/audio.html`

```
<figure {{ with .Get "class" }}class="{{ . }}"{{ end }}>
  <audio controls preload="{{ .Get "preload" | default "metadata" }}">
    {{ with .Get "src" }}<source src="{{ . | relURL }}" type="audio/mpeg">{{ end }}
  </audio>
  {{ with .Get "caption" }}<figcaption>{{ . }}</figcaption>{{ end }}
</figure>
```

And shortcode:

```
{ { < audio src="/audio/file.mp3" caption="Caption" > } }
```