---
comments: true
date: "2021-08-13T00:00:00Z"
description: How prioritise requests to improve website speed
summary: How to prioritise requests to improve website speed
categories:
- article
tags:
- html
title: Prioritise requests to improve website speed
---

With the `preload`, `preconnect` and `prefetch` attribute in HTML, you can implement different loading strategies for high priority resources. Browsers use this heuristic resource priority to delay sending certain requests in order to avoid bandwidth contention of these resources with more critical ones. This ensures they are available earlier and are less likely to block the page's render, improving performance.

`<link rel="preload">` lets you declare fetch requests in the HTML's `<head>`, specifying resources that your page will need very soon, which you want to start loading early in the page lifecycle, before browsers' main rendering machinery kicks in. This ensures they are available earlier and are less likely to block the page's render, improving performance.

`<link rel="preconnect">` element is a hint to browsers that the user is likely to need resources from the target resource's origin, and therefore the browser can likely improve the user experience by preemptively initiating a connection to that origin.

`<link rel="prefetch">` element is a hint to browsers that the user is likely to need the target resource for future navigations, and therefore the browser can likely improve the user experience by preemptively fetching and caching the resource.