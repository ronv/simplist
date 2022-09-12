---
comments: true
date: "2020-10-29T00:00:00Z"
description: Implement sharing via URL
published: true
summary: Implement sharing via URL
categories:
- article
tags:
- javascript
- social
title: Social sharing buttons without Javascript
---

I you are concerned about privacy or page load speed might want to drop "heavyweight" dynamic social sharing buttons altogether and implement sharing via URL instead. You can use custom sharing links that don’t run any outside Javascript. 

## Twitter

```
<a href="https://twitter.com/intent/tweet?url=YOUR-URL&text=YOUR-TITLE&via=YOUR-TWITTERHANDLE">Twitter</a>
```

## Facebook

```
<a href="https://facebook.com/sharer/sharer.php?u=YOUR-URL">Facebook</a>
```

## LinkedIn

```
<a href="http://www.linkedin.com/shareArticle?mini=true&url=YOUR-URL&title=YOUR-TITLE&summary=YOUR-SUMMARY">LinkedIn</a>
```

## Pinterest

```
<a href="http://pinterest.com/pin/create/button/?url=YOUR-URL&media=YOUR-IMAGE-URL&description=YOUR-DESCRIPTION">Pinterest</a>
```

## Reddit 

```
<a href="http://www.reddit.com/submit?url=YOUR-URL&title=YOUR-TITLE" target="_blank" title="Share on Reddit">Reddit</a>
```

## Pinboard

```
<a href="https://pinboard.in/popup_login/?url=YOUR-URL&title=YOUR-TITLE" target="_blank" title="Share on Pinboard">Pinboard</a>
```

## E-mail

```
<a href="mailto:?subject=SUBJECT&body=:BODY" target="_blank" title="Email">E-mail</a>
```

## VKontakte

```
<a href="https://vk.com/share.php?url=YOUR-URL" target="_blank">VK</a>
```