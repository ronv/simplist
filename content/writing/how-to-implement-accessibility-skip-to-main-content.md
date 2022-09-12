
---
title: How to implement accessibility "Skip to main content"
date: 2021-04-13T19:06:55.722Z
description: Accessible "Skip to main content" link
categories:
- article
tags:
  - Hugo
  - Accessibility
---

When users with assistive technology interact with your site they use the tab key to jump from link to link. If you have a lot of links at the first of your page in your header or in a menu, they must tab through those every time they come to a new page just to get to the main content. Providing a “skip to main content” link allows your user to easily skip to the main content of the page with a simple link without needing to go through repetitive elements like long list of navigation links, sub-lists of links that appear on every page. Use a skip link to let users bypass this content.

## How does "Skip to main content" work?

A skip link is an offscreen anchor that is always the first focusable item in the DOM. Typically, it contains an in-page link to the main content of the page. Because it is the first element in the DOM, it only takes a single action from assistive technology to focus it and bypass repetitive navigation. Make sure the "Skip to main content" link is one of the first items that screen readers hear and that keyboard users tab to. Otherwise, users may not realize there is a "Skip to main content" link there at all, and may waste time trying to muddle through the extraneous links. Screen reader users especially may get impatient if they don't hear the "Skip to main content" link very early in the page.

## How to implement "Skip to main content"?

Provide a link at the top of the page which jumps the user down to an anchor or target at the beginning of the main content. Activating the link sets focus beyond the other content to the main content. This technique is most useful when a page has one main content area, rather than a set of content areas that are equally important, and when there are not multiple navigation sections on the page.

```
<!-- index.html -->
<a class="skip-link" href="#main">Skip to main content</a>
…
<main id="main" tabindex="-1">
  Main content
</main>
```

```
/* style.css */
.skip-link {
  position: absolute;
  top: -50px;
  left: 0;
  background: #eee;
  z-index: 100;
}

.skip-link:focus {
  top: 0;
}
```

You should include a tabindex=”-1″ on the target of the skip link. IE and Chrome both require this attribute to be present to make the skip link work consistently.

Read about the [skip to main content implementation on the W3C’s Web Accessibility Initiative’s homepage](https://www.w3.org/TR/WCAG20-TECHS/G1.html).

