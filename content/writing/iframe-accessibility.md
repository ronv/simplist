---
comments: true
date: "2019-11-18T00:00:00Z"
description: Iframe accessibility
summary: Iframe accessibility
categories:
- article
tags:
- html
title: "Iframe accessibility"
---

For iframes that have meaningful content, provide a title using the `title` attribute.

```
<iframe title="Cat dancing video" src="catdancingvideo.html"></iframe>
```

For iframes that contain non-readable content, provide a title to pass automated tests, but be sure to hide the content altogether from screen reader users using `aria-hidden="true"`.

```
<iframe title="Non-readable content" src="non-readable-content.com" aria-hidden="true"></iframe>
```