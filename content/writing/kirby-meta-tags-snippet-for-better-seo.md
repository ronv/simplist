---
comments: true
date: "2020-09-11T00:00:00Z"
description: How to create the right meta description for Kirby
summary: How to create the right meta description for Kirby
categories:
- article
tags:
- kirby
title: Kirby meta tags snippet for better SEO
---

Meta tags are snippets of HTML code capable of being crawled by search engine robots such as Google. Invisible to site visitors, if handled skilfully they can have a huge effect on SEO. Google can use this information to create rich snippets or enable sorting of search results. 

This is example code I use for Kirby websites:

```

<link rel="canonical" href="<?php echo html($page->url()) ?>" />
    <?php if($page->isHomepage()): ?>
      <title><?php echo html($site->title()) ?></title>
    <?php else: ?>
      <title><?php echo $page->title()->html() ?> | <?php echo $site->title()->html() ?></title>
    <?php endif ?>

    <?php if($page->isHomepage()): ?>
    <meta name="description" content="<?php echo $site->description()->html() ?>">
    <?php else: ?>
    <meta name="description" content="<?php echo $page->text()->excerpt(140) ?>">
    <?php endif ?>

    <meta name="publisher" content="<?php echo html($site->author()) ?>" />
    <meta name="copyright" content="<?php echo html($site->author()) ?>" />
    <meta name="robots" content="index,follow" />
    <?php if($page->isHomepage()): ?>
    <meta property="og:title" content="<?php echo html($site->title()) ?>" />
    <?php else: ?>
    <meta property="og:title" content="<?php echo html($page->title()) ?> | <?php echo html($site->title()) ?>" />
    <?php endif ?>
    <?php if($page->isHomepage()): ?>
    <meta property="og:type" content="website" />
    <?php else: ?>
    <meta property="og:type" content="article" />
    <?php endif ?>
    <meta property="og:url" content="<?php echo html($site->url()) ?>" />
    <meta property="og:image" content="<?php echo url('assets/images/image.png') ?>" />

    <?php if($page->isHomepage()): ?>
    <meta property="og:description" content="<?php echo html($site->description()) ?>" /><?php else: ?>
    <meta property="og:description" content="<?php echo html($page->text()->excerpt(140)) ?>
    <?php endif ?>

    <?php if($page->isHomepage()): ?>
    <meta itemprop="name" content="<?php echo html($site->title()) ?>">
    <?php else: ?>
    <meta itemprop="name" content="<?php echo html($page->title()) ?> | <?php echo html($site->title()) ?>">
    <?php endif ?>
    <?php if($page->isHomepage()): ?>
    <meta itemprop="description" content="<?php echo html($site->description()) ?>">
    <?php else: ?>
    <meta itemprop="description" content="<?php echo html($page->text()->excerpt(140)) ?>">
    <?php endif ?>

```