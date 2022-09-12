---
title: 'RSS feeds for your Github releases, tags and activity'
date: 2020-03-26T08:44:50.666Z
description: Find out about latest from projects you follow via RSS feed
categories:
- article
tags:
  - rss
---
GitHub provides several timeline resources in [Atom](http://en.wikipedia.org/wiki/Atom_(standard)) format. That's how I get latest info about projects that I follow and their fixed bugs and new features. Some of official RSS feeds are:

```
/* Repo releases */

https://github.com/:owner/:repo/releases.atom

/* Repo commits */

https://github.com/:owner/:repo/commits.atom

/* Private feed (You can find Subscribe to your news feed in dashboard page after login) */

https://github.com/:user.private.atom?token=:secret

/* Repo tags */

https://github.com/:user/:repo/tags.atom

/* User activity */

https://github.com/:user.atom
```