---
comments: true
date: "2019-01-23T00:00:00Z"
description: Outlook Conditional CSS
summary: Outlook Conditional CSS
categories:
- article
tags:
- css
title: "Outlook Conditional CSS"
---

To provide an Outlook-specific stylesheet you can use Microsoft’s conditional comments and they can be placed after your main CSS:

```
<!--[if gte mso 9]>
    <style type="text/css">
    /* Your Outlook-specific CSS goes here. */
    </style>
<![endif]-->
```