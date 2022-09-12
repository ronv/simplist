---
comments: true
date: "2019-06-19T00:00:00Z"
description: The caret-color CSS property
summary: The caret-color CSS property
categories:
- article
tags:
- css
title: "The caret-color CSS property"
---

You can change color of the insertion caret, the visible marker where the next character typed will be inserted. The caret appears in elements such as `<input>` or those with the `contenteditable` attribute:

```
input {
  caret-color: blue;
}

textarea {
  caret-color: green;
}
```
```
<h1 contenteditable="true">
  This is editable heading.
</h1>

h1 {
  caret-color: blue;
}
```