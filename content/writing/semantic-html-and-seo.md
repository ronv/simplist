---
date: "2019-12-04T00:00:00Z"
description: Using semantic HTML tags to improve SEO.
summary: Using semantic HTML tags to improve SEO.
categories:
- article
tags:
- seo
- html
title: Semantic HTML and SEO
---
One of the most important features of HTML5 is its semantics. Semantic HTML allow you to add meaning to your markup so that search engines, screen readers, and web browsers can make sense of it. If you use HTML5 semantics wisely you can make your website more accessible, improve user experience, and get better search engine rankings as well. Good semantic HTML5 structure is key for enhancing web accessibility.

Examples of non-semantic HTML elements:

```html
<div></div><span></span>
```

Examples of semantic HTML elements:

```html
<header></header><main></main><footer></footer>
```

It is well known that standard HTML semantic elements (`<h1>`, `<title>`, etc.) are used by Google and other search engines as a core ranking metric. Semantic HTML highlight the most important parts of your page to let it stand out in SERPs, which allows users to encounter your content. It seems a logical progression from the current practice of search engines to adopt HTML5 semantic elements into their ranking algorithms.

By default, search engine bots don’t understand the structure of your content. Semantic HTML5 tags have a specific role to play and tell us what kind of content we can expect them to contain. Apart from giving context to content, semantic tags can also be used to assign priority to sections of content. Using semantic HTML5 tags focuses on the real specific content of the page and excludes other content that may be detrimental to to the theme. 

### Semantic HTML page layout

Example of non-semantic HTML page layout:

```html
<html>
    <head>
        <title>Your site</title>
    </head>
    <body>
        <div id="header">
            Logo, navigation.
        </div>
        <div id="main-content">
            Main content
        </div>
        <div id="footer">
            Footer
        </div>
    </body>
</html>
```

Example of semantic HTML page layout:

```html
<html>
    <head>
        <title>Your site</title>
    </head>
    <body>
        <header>
            Logo, navigation.
        </header>
        <main>
            Main content
        </main>
        <footer>
            Footer
        </footer>
    </body>
</html>
```

Difference between these 2 layouts: we have replaced `div` tags with 3 new tags: `header`, `main`, and `footer`. Those tags are semantic because they are used to represent different sections on an HTML page. Correctly using the correct semantic HTML tags in the place of `<div>` simply makes that same understanding easier for machines. HTML5 semantics is an important step of creating content that ranks well in Google and other search engines.
