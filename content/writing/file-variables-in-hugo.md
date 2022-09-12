---
comments: true
date: "2021-08-11T00:00:00Z"
description: File variables in Hugo
summary: File variables in Hugo
categories:
- article
tags:
- hugo
title: File variables in Hugo
---

The `.File` variable gives you additional information of a page. `.File` is only accessible on pages that has a content page attached to it.

The `.File` object contains the following fields:

- `.File.Path` -  path of the page, relative to the content dir (e.g., `articles/post.md`).
- `.File.LogicalName` - the name of the page file (e.g., `post.md`).
- `.File.TranslationBaseName` - the name of the file without extension (e.g., `post`).
- `.File.ContentBaseName` - is a either `TranslationBaseName` or name of folder if file is a leaf bundle.
- `.File.BaseFileName` the filename without extension (e.g., `post`).
- `.File.Ext` - file extension (e.g., `md`).
- `.File.Lang` - language if Hugo’s multilingual features are enabled (e.g., `en`).
- `.File.Dir` - the path `content/articles/abc/def/`, the relative directory path of the content file will be returned, e.g. `articles/abc/def/`.
- `.File.UniqueID` - MD5-checksum of the content file’s path.





