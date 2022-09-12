---
layout: post
comments: true
date: "2021-02-21T00:00:00Z"
description: Disable FLoC on Netlify
summary: Disable FLoC on Netlify
categories:
- article
tags:
- netlify
- security
title: Disable FLoC on Netlify
---

FLoC (Federated Learning of Cohorts) enables ad selection without sharing the browsing behaviour of individual users. As a user moves around the web, their browser uses the FLoC algorithm to work out its "interest cohort", which will be the same for thousands of browsers with a similar recent browsing history. The browser recalculates its cohort periodically, on the user's device, without sharing individual browsing data with the browser vendor or anyone else.

## How can I opt out?

If you are a website owner, your site will automatically be included in FLoC calculations if it accesses the FLoC API or if Chrome detects that it serves ads. You can opt out of this calculation by sending the following HTTP response header (`netlify.toml`):


```
[[headers]]
    for = "/*"
    [headers.values]
        Permissions-Policy = "interest-cohort=()"

```





