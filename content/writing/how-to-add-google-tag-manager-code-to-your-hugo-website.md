---
title: How to add Google Tag Manager code to your Hugo website
date: 2020-06-12T12:18:01.739Z
description: How to add Google Tag Manager container and dataLayer to your Hugo website.
categories:
- article
tags:
  - hugo
---
In `config.toml` add new params and change XXX’s with your containerID.

```
[params]   
   gtm = "GTM-XXXXXX"
```

Find your themes `header.html` partial and add Google Tag Manager code anywhere between the `<head>` tags.

```
{{ if $.Site.Params.gtm }}
  <!-- Google Tag Manager -->
  <!-- create dataLayer -->
  <script>
   <!-- OPTIONAL dataLayer -->
    var dataLayer = window.dataLayer = window.dataLayer || [];
    dataLayer.push({
      page:'{{ .Title }}',
      categories:'Your dataLayer'
    });
  </script>
  <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
  new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
  j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
  'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
  })(window,document,'script','dataLayer','{{ $.Site.Params.gtm }}');</script>
  <!-- End Google Tag Manager -->
  {{ end }}
```

Right below the `<body>` element, include the following code snippet.

```
{{ if $.Site.Params.gtm }}
    <!-- Google Tag Manager (noscript) -->
    <noscript><iframe src="https://www.googletagmanager.com/ns.html?id={{ $.Site.Params.gtm }}"
    height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
    <!-- End Google Tag Manager (noscript) -->
 {{ end }}
```

You may want to add `preconnect` and `prefetch` features for better performance.

```
<link href="https://www.googletagmanager.com" rel="preconnect" crossorigin>
<link rel="dns-prefetch" href="https://www.googletagmanager.com">
```

To exclude Google Tag Manager code from the localhost website, copy your code into an if statement like this:

```
{{ if not (in (.Site.BaseURL | string) "localhost") }}
...
{{ end }}
```

That's it!