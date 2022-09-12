---
comments: true
date: "2021-10-25T00:00:00Z"
description: How to add HTTP Headers for Cloudflare Pages
summary: Headers for Cloudflare Pages
categories:
- article
tags:
- cloudflare
- security
title: Headers for Cloudflare Pages
---

Cloudflare Pages now natively supports custom headers on your projects. Create a `_headers` plain text file in the output folder (build directory, not root) of your project, define the rules you want to apply. Changes to headers will be updated to your website at build time, so make sure you commit and push the file to trigger a new build each time you update headers.

Example (this sites `_headers` file):

```
/*
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  Referrer-Policy: no-referrer
  X-xss-protection: 1
  Strict-transport-security: max-age=31536000; preload

https://website-2021-oct.pages.dev/*
  X-Robots-Tag: noindex
```

First part of code is for main site, second is for pages.dev site. To prevent your pages.dev deployment from being indexed, you can add the following to your `_headers` file:

```
https://example-site.pages.dev/*
  X-Robots-Tag: noindex
```

Header rules are defined in multi-line blocks. The first line of a block is the URL or URL pattern where the rule's headers should be applied. On the next line, an indented list of header names and header values must be written:

```
[url]
  [haeder name]: [header value]
```

## Header examples

Access-Control-Allow-Origin (Indicates whether the response can be shared with requesting code from the given origin):

```
/*
  Access-Control-Allow-Origin: *
```

X-Robots-Tag (Prevent your pages.dev deployments showing in search results):
```
https://example.pages.dev/*
  X-Robots-Tag: noindex
```
X-Content-Type-Options (Used to protect against MIME sniffing vulnerabilities):

```
X-Content-Type-Options: nosniff
```
Referrer-Policy (Controls how much referrer information (sent with the Referer header) should be included with requests):

```
Referrer-Policy: no-referrer
```

Permissions-Policy (A header policy is a list of policy directives delivered via an HTTP header with a document):

```
Permissions-Policy: fullscreen=(), geolocation=()
```

X-xss-protection (Enables an XSS detection feature in the browser, which prevents some categories of XSS attacks, a common JavaScript vulnerability type):

```
X-xss-protection: 1
```

