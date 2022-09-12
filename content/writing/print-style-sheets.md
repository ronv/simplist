---
comments: true
date: "2018-04-22T00:00:00Z"
description: Print style sheets
summary: Print style sheets
categories:
- article
tags:
- css
- html
title: "Print style sheets"
---

A print style sheet can be added to the HTML `<head>`:

```
<link rel="stylesheet" href="main.css" />
<link rel="stylesheet" media="print" href="print.css" />
```

To separate screen and print media:

```
<link rel="stylesheet" media="screen" href="main.css" />
<link rel="stylesheet" media="print" href="print.css" />
```

Print styles can be included within an existing CSS file using `@media` rules:

```
/* on-screen styles */
@media screen {

  body {
    background: #000;
  }

}

/* print styles */
@media print {

  body {
    background: #fff;
  }

}
```

