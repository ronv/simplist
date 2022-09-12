---
title: How to create a theme for Hugo
date: 2020-06-30T19:06:55.722Z
description: How to create a theme in Hugo
categories:
- article
tags:
  - Hugo
---
### Install Hugo

First, install Hugo on your machine. For more information, read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo.

### Generate a new theme

Hugo doesn’t ship with a default theme, but it comes with a command to generate it. Run the following command after installing Hugo `hugo new site [name]`, after that, navigate into the root of the new Hugo folder and run command `hugo new theme [theme_name]` to generate the skeleton of a theme.

### File structure

```
.
└── theme-name
    ├── LICENSE
    ├── archetypes
    │   └── default.md
    ├── layouts
    │   ├── 404.html
    │   ├── _default
    │   │   ├── baseof.html
    │   │   ├── list.html
    │   │   └── single.html
    │   ├── index.html
    │   └── partials
    │       ├── footer.html
    │       ├── head.html
    │       └── header.html
    ├── static
    │   ├── css
    │   └── js
    └── theme.toml
```

`LICENSE`

By default, Hugo applies the MIT license to your theme.

`archetypes`

You can create new content files in Hugo using the `hugo new` command. If your theme makes use of specific keys in the front matter, it is a good idea to provide an archetype for each content type you have. By default, Hugo will create new content files with at least `date`, `title` and `draft = true`. 

`content`

All content for your website will live inside this directory.

`layouts`

The layouts directory contains all the HTML files that are used for generating HTML from the Markdown files. Templates include list pages, your homepage, taxonomy templates, partials, single-page templates, and more.

`static`

Stores all the static content: images, CSS, JavaScript, etc.

`theme.toml`

The `theme.toml` file contains information about the theme such as the name of the theme, license, description, author, etc.

If you’re developing a real theme, please remember to fill out files `theme.toml` and `LICENSE.md`.

### Add content

You can use the `new` command to add title and date:

```
hugo new posts/my-first-post.md
```

When we created our site, Hugo created a default archetype in the `/archetype/`folder.

### Make changes to your theme files

Now we have a basic template upon which we can start building our theme. What's next? I recommend a deep dive into the [docs](https://gohugo.io/documentation/) and check how to costumize your newly created theme. As for where to deploy your site, since Hugo is a static site generator, you can host it almost anywhere.