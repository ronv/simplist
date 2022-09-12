---
title: JSON-LD for Hugo
date: 2020-08-24T14:47:16.182Z
description: JSON-LD code snippet for Hugo website
categories:
- article
tags:
  - hugo
  - seo
---
JSON-LD is a lightweight Linked Data format. JSON-LD stands for JavaScript Object Notation for Linked Data, which consists of multi-dimensional arrays. It is easy for humans to read and write. It is based on the already successful JSON format and provides a way to help JSON data interoperate at Web-scale. It is an implementation format for structuring data analogous to Microdata and RDFa. Typically, in terms of SEO, JSON-LD is implemented leveraging the Schema.org vocabulary, a joint effort by Google, Bing, Yahoo!, and Yandex to create a unified structured data vocabulary for the web. By adding structured data to your Hugo site can give you a significant SEO boost and increase your rankings.

This is code snippet I use on my blog. You can add it as partial or just copy between `<head></head>` tags.

```
{{ if .IsHome -}}
<script type="application/ld+json">
{
    "@context": "http://schema.org",
    "@type": "WebSite",
    "name": "{{ .Site.Title }}",
    "url": "{{ .Site.BaseURL }}",
    "description": "{{ .Site.Params.description }}",
    "thumbnailUrl": "{{ .Site.Params.Logo | absURL }}",
    "license": "{{ .Site.Params.Copyright }}"
}
</script>
{{ else if .IsPage }}
{{ $author :=  or (.Params.author) (.Site.Author.name) }}
{{ $organization :=  .Site.Title }}
<script type="application/ld+json">
{
    "@context": "http://schema.org",
    "@type": "BlogPosting",
    "articleSection": "{{ .Section }}",
    "name": "{{ .Title | safeJS }}",
    "headline": "{{ .Title | safeJS }}",
    "alternativeHeadline": "{{ .Params.lead }}",
    "description": "{{ if .Description }}{{ .Description | safeJS }}{{ else }}{{if .IsPage}}{{ .Summary  }}{{ end }}{{ end }}",
    "inLanguage": {{ .Site.LanguageCode | default "en-us" }},
    "isFamilyFriendly": "true",
    "mainEntityOfPage": {
        "@type": "WebPage",
        "@id": "{{ .Permalink }}"
    },
    "author" : {
        "@type": "Person",
        "name": "{{ $author }}"
    },
    "creator" : {
        "@type": "Person",
        "name": "{{ $author }}"
    },
    "accountablePerson" : {
        "@type": "Person",
        "name": "{{ $author }}"
    },
    "copyrightHolder" : "{{ $organization }}",
    "copyrightYear" : "{{ .Date.Format "2006" }}",
    "dateCreated": "{{ .Date.Format "2006-01-02T15:04:05.00Z" | safeHTML }}",
    "datePublished": "{{ .PublishDate.Format "2006-01-02T15:04:05.00Z" | safeHTML }}",
    "dateModified": "{{ .Lastmod.Format "2006-01-02T15:04:05.00Z" | safeHTML }}",
    "publisher":{
        "@type":"Organization",
        "name": {{ $organization }},
        "url": {{ .Site.BaseURL }},
        "logo": {
            "@type": "ImageObject",
            "url": "{{ .Site.Params.logo | absURL }}",
            "width":"32",
            "height":"32"
        }
    },
    "image": {{ if .Params.images }}[{{ range $i, $e := .Params.images }}{{ if $i }}, {{ end }}{{ $e | absURL }}{{ end }}]{{ else}}{{.Site.Params.logo | absURL }}{{ end }},
    "url" : "{{ .Permalink }}",
    "wordCount" : "{{ .WordCount }}",
    "genre" : [ {{ range $index, $tag := .Params.tags }}{{ if $index }}, {{ end }}"{{ $tag }}" {{ end }}],
    "keywords" : [ {{ range $index, $tag := .Params.tags }}{{ if $index }}, {{ end }}"{{ $tag }}" {{ end }}]
}
</script>
{{ end }}
```

And settings for `config` file.

```
baseURL = "https://ronaldsvilcins.com/"
languageCode = "en-us"
title = "Ronalds Vilcins"

[params]
  description = "A design-minded full-stack developer and digital advertiser."
  author = "Ronalds Vilcins"
  copyright = "Ronalds Vilcins"
  logo = "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNk+A8AAQUBAScY42YAAAAASUVORK5CYII="
```