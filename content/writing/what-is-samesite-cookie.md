---
date: "2020-02-15T00:00:00Z"
description: SameSite cookies explained.
summary: SameSite cookies explained.
categories:
- article
tags:
- security
title: What is SameSite cookie?
---

The `SameSite` attribute can be used to control whether and how cookies are submitted in cross-site requests. Current behavior allows third-party websites to access all cookies by default. This creates the possibility of [cross-site request forgery](https://developer.mozilla.org/en-US/docs/Glossary/CSRF) (CSRF) attacks, other security vulnerabilities and privacy leaks. The `SameSite` cookie attribute restricts this browser behavior and prevent the browser from sending the cookie's key-value pair based on the type of interaction that triggered the HTTP request. 

Chrome, Firefox and others will be changing their default behavior in line with the IETF proposal, [Incrementally Better Cookies](https://tools.ietf.org/html/draft-west-cookie-incrementalism-00) and will begin enforcing a new secure-by-default cookie classification system, treating cookies that have no declared `SameSite` value as  `SameSite=Lax` cookies. Only cookies set as `SameSite=None; Secure` will be available in third-party contexts, provided they are being accessed from secure connections.

According to the online traffic monitor [StatCounter](https://gs.statcounter.com/browser-market-share), Chrome is the most popular web browser, and this change will affect 64% of the world’s internet users in 2020. These changes will also dramatically impact advertisers, publishers, or any company relying on cookies to target their audience. Be sure to prepare in advance so your users won't experience disruptions.

### Chrome 80 update

From 4th of february this will become the default behavior in Chrome 80. If you currently provide cookies that are intended for cross-site usage you will need to make changes.

### How to implement `SameSite`

For cookies where they are only needed in a first-party context you should ideally mark them as `SameSite=Lax` or `SameSite=Strict` depending on your needs. You can also choose to do nothing and just allow the browser to enforce its default, but this comes with the risk of inconsistent behavior across browsers and potential console warnings for each cookie.

For cookies needed in a third-party context, you will need to ensure they are marked as `SameSite=None; Secure`. Note that you need both attributes together. If you just specify `None` without `Secure` the cookie will be rejected.

### Accepted attribute values for `SameSite`

`strict` - The browser will only send cookies for first-party context requests (requests originating from the site that set the cookie). If the request originated from a different URL than that of the current location, none of the cookies tagged with the Strict attribute will be sent.

`lax` - Cookies will be sent automatically only in a first-party context and with HTTP GET requests. SameSite cookies will be withheld on cross-site sub-requests, such as calls to load images or iframes, but will be sent when a user navigates to the URL from an external site, e.g., by following a link.

`none` - Cookies will be sent in both first-party context and cross-origin requests; however, the value must be explicitly set to None and all browser requests must follow the HTTPS protocol and include the Secure attribute which requires an encrypted connection. Cookies that don't adhere to that requirement will be rejected.
Both attributes are required together. If just None is specified without Secure or if the HTTPS protocol is not used, the third-party cookie will be rejected.

