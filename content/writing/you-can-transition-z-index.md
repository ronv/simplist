---
comments: true
date: "2015-08-11T00:00:00Z"
description: You can transition z-index
summary: You can transition z-index
categories:
- article
tags:
- css
title: "You can transition z-index"
---

You can transition `z-index`:

```
@keyframes move {
  from { z-index: 0; transform: scale(1); }
  to { z-index: 4; transform: scale(2.5); }
}
```