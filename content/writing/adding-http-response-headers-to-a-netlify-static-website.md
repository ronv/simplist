---
comments: true
date: "2019-05-23T00:00:00Z"
description: Increase the security of your Netlify website by adding security headers
summary: Increase the security of your Netlify website by adding security headers.
categories:
- article
tags:
- netlify
- security
title: Adding HTTP response headers to a Netlify static website
---

HTTP stands for "Hypertext Transfer Protocol". Almost everything you see in your browser is transmitted to your computer over HTTP. HTTP headers are the core part of these HTTP requests and responses, and they carry information about the client browser, the requested page, the server and more. The ability to configure your HTTP headers allows you to do things such as define your Cache Control, Content Security Policy your X Frame Options, and all kinds of other important things to help control security of your website.

Netlify allows you to set additional HTTP response headers in a file called ```_headers``` or as part of a ```[[headers]]``` section of your ```netlify.toml``` file. If you decide to add HTTP response headers in ```_headers``` file then put it in your deployed directory. Some static site generators, like Jekyll, may also require additional configuration to avoid exclusion of files that begin with``` _```. (For Jekyll, this requires adding an include parameter to ```_config.yml```.) ```_headers``` or ```netlify.toml``` file  allows you to define headers for different URLs (for example ```/about```) or URL segments (for example ```/*``` for all URLs) of your website.

Here’s a sample ```_headers``` setup:

```
/*
 X-Frame-Options: DENY
 X-XSS-Protection: 1; mode=block
 Referrer-Policy: no-referrer
 X-Content-Type-Options: nosniff
```

The equivalent ```netlify.toml``` file:

```
[[headers]]
  for = "/*" # This defines which paths this specific [[headers]] block will cover.
  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    Referrer-Policy = "no-referrer"
    X-Content-Type-Options = "nosniff"
```

To add ```Cache-Control``` for static assets simply add these lines to ```netlify.toml``` file:

```
[[headers]]
  for = "*.css"
  [headers.values]
    Cache-Control = "max-age=604800, public"

[[headers]]
  for = "*.js"
  [headers.values]
    Cache-Control = "max-age=604800, public"
```

or in ```_headers``` file:

```
/*.css
  Cache-Control: public, s-max-age=604800
  
/*.js
  Cache-Control: public, s-max-age=604800
```





