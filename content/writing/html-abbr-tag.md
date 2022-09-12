---
comments: true
date: "2017-02-21T00:00:00Z"
description: HTML abbr tag
summary: HTML abbr tag
categories:
- article
tags:
- html
title: "HTML abbr tag"
---

The `<abbr>` tag defines an abbreviation or an acronym, like "HTML", "CSS", "Mr.". Use the `title` attribute to show the description for the abbreviation when you mouse over the element:

```
<abbr title="Cascading Style Sheets">CSS</abbr>
```

`<abbr>` can also be used with `<dfn>` to define an abbreviation:

```
<p><dfn><abbr title="Cascading Style Sheets">CSS</abbr>
</dfn> describes the style of an HTML document.</p>

```

You can style abbr tag like this:

```
abbr {
  text-decoration: underline red dotted;
  color: red;
}

abbr:hover {
  cursor: help;
}
```

