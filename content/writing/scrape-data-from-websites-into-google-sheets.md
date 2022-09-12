---
comments: true
date: "2022-06-03T00:00:00Z"
description: How To Use IMPORTXML in Google Sheets
summary: How To Use IMPORTXML in Google Sheets
categories:
- article
tags:
- excel
- google
title: Scrape data from websites into Google Sheets
---

Want to grab data from the internet? Google Sheets has a built-in function called `ImportXML` which can be used to scrape publicly available structured data from websites. `ImportXML` imports data from any of various structured data types including XML, HTML, CSV, TSV, and RSS and ATOM XML feeds.

## Syntax of the ImportXML function

```
IMPORTXML(url, xpath_query)
```

`url` - The URL of the page to examine, including protocol (e.g. http://).
The value for `url` must either be enclosed in quotation marks or be a reference to a cell containing the appropriate text.

`xpath_query` - The XPath query to run on the structured data.

## XPath Query

XPath is a major element in the XSLT standard. XPath can be used to navigate through elements and attributes in an XML document. The xpath_query argument is the XPath query to run on the data of the given URL. XPath is a query language used to retrieve pieces of information from websites.

Google Chrome includes the ability to copy Xpath as part of its DevTools feature. To access it, inspect the element you’re interested in by right-clicking it and selecting Inspect. In the elements panel, right-click the element you’ve highlighted and Copy > Copy XPath.

## Common XPath queries include:

- `//h1 ` – All `h1`;
- `//title` – All titles;
- `//meta[@name='description']/@content` – Meta description;
- `//@href` – All links;
- `//a[contains(@href, ‘example.com’)]/@href` - All internal links;
- `//a[not(contains(@href, ‘example.com’))]/@href` - All external links;
- `//link[@rel=’canonical’]/@href` – Any canonical;
- `//*[@itemtype]/@itemtype` – Types of schema;
- `//*[@hreflang]` – hreflang attributer;
- `//meta[@name=’robots’]/@content` - robots.

## Sample usage

```
IMPORTXML("https://en.wikipedia.org/wiki/Moon_landing", "//a/@href")

IMPORTXML(A2,B2)
```













