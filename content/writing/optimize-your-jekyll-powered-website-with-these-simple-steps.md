---
comments: true
date: "2019-10-29T00:00:00Z"
description: How to optimize your Jekyll website for search engines, accessibility,
  and performance
published: true
summary: How to optimize your Jekyll website for search engines, accessibility, and performance.
categories:
- article
tags:
- seo
- jekyll
title: Optimize your Jekyll powered website with these simple steps
---

Having a website which ranks highly in search engine results, loads quickly will increase your traffic and improve the performance and return of your marketing investment. If you have good SEO (Search Engine Optimization), you can attract more traffic and get more opportunities to convert potential customers. Between research, site edits, copywriting, and link building, getting a website to the top of SERP (Search Engine Results Page) is no easy task. To ensure your website stands out from the crowd, and helps you pull in the leads that you need, follow these simple tips below for easy website optimization. 

Most of the optimizations can be implemented by using Jekyll plugin called ```jekyll-seo-tag```. It's a Jekyll plugin to add metadata tags for search engines and social networks to better index and display your site's content.

[Jekyll SEO tag](https://github.com/jekyll/jekyll-seo-tag) adds the following meta tags to your site:

* Page title, with site title or description appended
* Page description
* Canonical URL
* Next and previous URLs on paginated pages
* [JSON-LD Site and post metadata](https://developers.google.com/search/docs/guides/intro-structured-data) for richer indexing
* [Open Graph](https://ogp.me/) title, description, site title, and URL (for Facebook, LinkedIn, etc.)
* [Twitter Summary Card](https://dev.twitter.com/cards/overview) metadata

While you could theoretically add the necessary metadata tags yourself, Jekyll SEO tag provides a battle-tested template of crowdsourced best-practices.

Here is how to install Jekyll SEO tag. Add the following to your site's `Gemfile`:

  ```ruby
  gem 'jekyll-seo-tag'
  ```
Add the following to your site's `_config.yml`:

  ```yml
  plugins:
    - jekyll-seo-tag
  ```

If you are using a Jekyll version less than `3.5.0`, use the `gems` key instead of `plugins`. Add the following right before `</head>` in your site's template(s):

  ```liquid
  {% seo %}
  ```

You can read more about advanced usage of Jekyll SEO tag [here](https://github.com/jekyll/jekyll-seo-tag).

Next, add sitemap to your website. What is a sitemap? A sitemap is a file where you provide information about the pages, videos, and other files on your site, and the relationships between them. Search engines like Google read this file to more intelligently crawl your site. A sitemap tells the crawler which files you think are important in your site, and also provides valuable information about these files: for example, for pages, when the page was last updated, how often the page is changed, and any alternate language versions of a page.

Jekyll websites will not have sitemap by default. You can always generate them using a plugin. Jekyll sitemap generator plugin will generate a sitemaps.org compliant sitemap for your Jekyll website. Add `gem 'jekyll-sitemap'` to your site's Gemfile and run `bundle`. This will create a sitemap for you with the link ```/sitemap.xml```.

```yml
url: "http://example.com" # the base hostname & protocol for your site
plugins:
  - jekyll-sitemap
```

Now, let's add a `robots.txt` file. A `robots.txt` file provides informations to crawlers on how to search and index pages. You should also specify the path to your sitemap. Create a `robots.txt` file in your root directory and paste the following code:
```
---
layout: none
---
User-agent: *
Sitemap: {{ site.url }}/sitemap.xml
```

Finally, we are done! Your website is now SEO optimized!






