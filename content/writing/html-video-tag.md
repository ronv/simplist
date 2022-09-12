---
comments: true
date: "2019-01-21T00:00:00Z"
description: HTML video tag
summary: HTML video tag
categories:
- article
tags:
- html
title: "HTML video tag"
---

The `<video>` tag is used to embed video content in a document, such as a movie or other video streams.

```
<video width="500" height="300" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  <track src="subtitle.vtt" kind="subtitles" />
  Your browser does not support the HTML5 video tag.
</video>
```

- `<video>` Defines the video element;
- `<source>`  Defines the video source;
- `<track>` Defines the text track.

The text between the `<video>` and `</video>` tags will only be displayed in browsers that do not support the `<video>` element.