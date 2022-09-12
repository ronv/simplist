---
date: "2017-11-10T00:00:00Z"
description: How to Redirect Pages in Jekyll
summary: How to Redirect Pages in Jekyll.
categories:
- article
tags:
- jekyll
title: Redirect Jekyll URLs
---

When a Jekyll post or page's title or date changes, existing links to the site may break. However, using the Jekyll Redirect From plugin, you can automatically redirect visitors to the updated URL.

Add this line to your application's Gemfile:

    gem 'jekyll-redirect-from'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install jekyll-redirect-from

Once it's installed into your evironment, add it to your `_config.yml`:

```yaml
plugins:
  - jekyll-redirect-from
```

If you are using a Jekyll version less than 3.5.0, use the `gems` key instead of `plugins`.

If you're using Jekyll in `safe` mode to mimic GitHub Pages, make sure to
add jekyll-redirect-from to your whitelist:

```yaml
whitelist:
  - jekyll-redirect-from
```

Then run `jekyll <cmd> --safe` like normal.


The object of this gem is to allow an author to specify multiple URLs for a
page, such that the alternative URLs redirect to the new Jekyll URL.

To use it, simply add the array to the YAML front-matter of your page or post:

```yaml
title: My amazing post
redirect_from:
  - /post/123456789/
  - /post/123456789/my-amazing-post/
```

Redirects including a trailing slash will generate a corresponding subdirectory containing an `index.html`, while redirects without a trailing slash will generate a corresponding `filename` without an extension, and without a subdirectory.

For example...

```text
redirect_from:
  - /post/123456789/my-amazing-post
```

...will generate the following page in the destination:

```text
/post/123456789/my-amazing-post
```

While...

```text
redirect_from:
  - /post/123456789/my-amazing-post/
```

...will generate the following page in the destination:

```text
/post/123456789/my-amazing-post/index.html
```

These pages will contain an HTTP-REFRESH meta tag which redirect to your URL.

You can also specify just **one url** like this:

```text
title: My other awesome post
redirect_from: /post/123456798/
```

If `site.url` is set, its value, together with `site.baseurl`, is used as a prefix for the redirect url automatically. This is useful for scenarios where a site isn't available from the domain root, so the redirects point to the correct path. If `site.url` is not set, only `site.baseurl` is used, if set.

If you are hosting your Jekyll site on [GitHub Pages](https://pages.github.com/), and `site.url` is not set, the prefix is set to the pages domain name i.e. http://example.github.io/project or a custom CNAME.

Sometimes, you may want to redirect a site page to a totally different website. This plugin also supports that with the `redirect_to` key:

```yaml
title: My amazing post
redirect_to: http://www.github.com
```

Using `redirect_to` or `redirect_from` with collections will only work with files which are output to HTML, such as `.md`, `.textile`, `.html` etc.


If you want to customize the redirect template, you can. Simply create a layout in your site's `_layouts` directory called `redirect.html`.

Your layout will get the following variables:

* `page.redirect.from` - the relative path to the redirect page
* `page.redirect.to` - the absolute URL (where available) to the target page