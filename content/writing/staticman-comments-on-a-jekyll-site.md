---
comments: true
date: "2019-07-23T00:00:00Z"
description: Generating comments on static sites with Staticman
summary: Generating comments on static sites with Staticman.
categories:
- article
tags:
- jekyll
title: Staticman comments on a Jekyll site
---

Staticman allows you to “bring user-generated content to static sites”. It works perfectly with Jekyll sites hosted on GitHub Pages, as a push to your main branch will regenerate the site automatically. If you want to moderate entries before they are published, a pull request will be created for your approval; otherwise, files will be pushed to your main branch straight away. Here is step by step guide how to add Staticman comments to your Jekyll site.

- Add Staticman to your repository

Go to ```https://github.com/apps/staticman-net``` and install the application on your repository.

- Add v3 endpoint, ```https://api.staticman.net/v3/entry/github/[YOUR USERNAME]/[YOUR REPOSITORY]/[BRANCH]/comments```. This line goes in ```_config.yml``` as the ```staticman_url``` variable.

```yaml
staticman_url: https://api.staticman.net/v3/entry/github/[YOUR USERNAME]/[YOUR REPOSITORY]/master/comments
```

- Add Staticman config file (```staticman.yml```) in root of site. Here are sample file:

```yaml
comments:
  # (*) REQUIRED
  #
  # Names of the fields the form is allowed to submit. If a field that is
  # not here is part of the request, an error will be thrown.
  allowedFields: ["name", "email", "url", "message"]

  # (*) REQUIRED
  #
  # Name of the branch being used. Must match the one sent in the URL of the
  # request.
  branch: "master"

  # Text to use as the commit message or pull request title. Accepts placeholders.
  commitMessage: "Add comments."

  # (*) REQUIRED
  #
  # Destination path (filename) for the data files. Accepts placeholders.
  filename: "entry{@timestamp}"

  # The format of the generated data files. Accepted values are "json", "yaml"
  # or "frontmatter"
  format: "yaml"

  # List of fields to be populated automatically by Staticman and included in
  # the data file. Keys are the name of the field. The value can be an object
  # with a `type` property, which configures the generated field, or any value
  # to be used directly (e.g. a string, number or array)
  generatedFields:
    date:
      type: date
      options:
        format: "timestamp-seconds"

  # Whether entries need to be appproved before they are published to the main
  # branch. If set to `true`, a pull request will be created for your approval.
  # Otherwise, entries will be published to the main branch automatically.
  moderation: true

  # Name of the site. Used in notification emails.
  name: "example.com"

  # Notification settings. When enabled, users can choose to receive notifications
  # via email when someone adds a reply or a new comment. This requires an account
  # with Mailgun, which you can get for free at http://mailgun.com.
  #notifications:
    # Enable notifications
    #enabled: true

    # (!) ENCRYPTED
    #
    # Mailgun API key
    #apiKey: "1q2w3e4r"

    # (!) ENCRYPTED
    #
    # Mailgun domain (encrypted)
    #domain: "4r3e2w1q"

  # (*) REQUIRED
  #
  # Destination path (directory) for the data files. Accepts placeholders.
  path: "_data/comments/{options.slug}"

  # Names of required fields. If any of these isn't in the request or is empty,
  # an error will be thrown.
  requiredFields: ["name", "email", "message"]

  # List of transformations to apply to any of the fields supplied. Keys are
  # the name of the field and values are possible transformation types.
  transforms:
    email: md5
```

- Add comments section to your post template

```
<!-- Comments -->
{% if site.data.comments[page.slug] %}
    <h3>
    {% if site.data.comments[page.slug].size > 1 %}
      {{ site.data.comments[page.slug] | size }}
    {% endif %}
    Comments:
    </h3>
  {% assign comments = site.data.comments[page.slug] | sort %}
    {% for comment in comments %}
      <label>
        {% if comment[1].url %}
          <a href="{{ comment[1].url }}">
        {% endif %}
        <strong>{{ comment[1].name }}</strong>
        {% if comment[1].url %}
          </a>
        {% endif %}
      </label>
      <em>{{ comment[1].date | date: "%B %d, %Y" }}</em>
      <p>{{ comment[1].message | markdownify }}</p>
    {% endfor %}
{% endif %}
<!-- Comments Form -->
  <form method="POST" action="{{ site.staticman_url }}">
    <input name="options[redirect]" type="hidden" value="https://example.com">
    <input name="options[slug]" type="hidden" value="{{ page.slug }}">
      <label>Name</label>
      <input name="fields[name]" type="text">
      <label>E-mail (optional)</label>
      <input name="fields[email]" type="email">
      <label>Website (optional)</label>
      <input name="fields[url]" type="url">
      <label>Message</label>
      <textarea style="width:100%" name="fields[message]" rows="12"></textarea>
      <small>Comments will appear after moderation.</small>
      <button type="submit">Submit comment</button>
  </form>
```

When the user fills out the form and clicks submit button the form is sent to Staticman application. Staticman application receives the comment info, processes it, and submits a comment file to GitHub as a pull request to the sites repository. Your comments will be saved in a comments folder ```_data/comments/{options.slug}```.