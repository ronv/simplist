---
title: HTML5 progress element
date: 2020-03-27T10:40:54.596Z
description: >-
  The <progress> element is used to create a progress bar to serve as a visual
  demonstration of progress
categories:
- article
tags:
  - html
---
HTML5 introduced the progress bar element, which allows us to show the progress of certain tasks, like uploads or downloads, basically anything that is in progress. The task itself is irrelevant, but displaying its progress is not. A progress element [must have](https://www.w3.org/TR/html-markup/progress.html) both a start tag (i.e.`<progress>`) and an end tag (i.e.`</progress>`). The progress value is determined with the `value`, `min` and `max` attributes, as follows.

```
<progress value="10" max="100"></progress>
```

The `value` attribute, if present, must have a value equal to or greater than zero, and less than or equal to the value of the `max` attribute, if present, or 1.0, otherwise. The `max` attribute, if present, must have a value greater than zero. The `<progress>` element is [fairly well-supported](http://caniuse.com/#feat=progressmeter) in today’s major browsers, although only in version 6+ of Safari (so not on Windows, as the last version there was 5.1) and only in version 10+ of Internet Explorer. If you need to show a result for something that is not related to a task, you should use `<meter>`.

### Styling progress element

As is usual with such elements, browsers have their own unique styling for the `<progress>` element. You can, however, override this to a certain extent using simple CSS. In CSS, we actually can use the element selector to target and add style rules to `<progress>` element.

```
progress {
   background-color:#ddd;
   border:0;
   height:20px;
   border-radius:5px;
}
```

However, each browser handles this a bit differently.

```
/* Firefox */

progress::-moz-progress-bar { background: #ddd; }

/* WebKit & Blink */

progress::-webkit-progress-bar { background: #ddd; }
progress::-webkit-progress-value { background: #000; }
```