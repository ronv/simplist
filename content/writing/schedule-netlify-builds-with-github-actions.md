---
title: 'Schedule Netlify builds with GitHub Actions'
date: 2020-12-23T08:44:50.666Z
description: How to schedule Netlify builds with GitHub Actions
categories:
- article
tags:
  - netlify
  - github
---

If you didn't already know it, GitHub Actions is a way to automate things in your GitHub repository. With it you can create workflows that can do things with your repository and react to different kinds of events. The easiest way to setup a scheduled build hook trigger that I have come across is to use GitHub Actions.

The `schedule` event allows you to trigger a workflow at a scheduled time. You can schedule a workflow to run at specific UTC times using POSIX cron syntax. Scheduled workflows run on the latest commit on the default or base branch. The shortest interval you can run scheduled workflows is once every 5 minutes.

This example triggers the workflow every 15 minutes:

```
on:
  schedule:
    # * is a special character in YAML so you have to quote this string
    - cron:  '*/15 * * * *'

```

## What are Netlify Build hooks?

Build hooks are URLs you can use to trigger new builds and deploys. You can find them in Netlify dashboard: *Site settings > Build & deploy > Continuous deployment > Build hooks*. By creating a build hook and sending a `POST` request to it, you trigger a new build & deploy for your site. 


## Workflow file

In your GitHub repo, create a `main.yml` file in a `.github/workflows` directory:

```
name: Shedule Netlify Build
on:
  schedule:
    - cron: '0 6 * * *'
jobs:
  build:
    name: Request Netlify Webhook
    runs-on: ubuntu-latest
    steps:
      - name: Curl request
        run: curl -X POST -d {} HERE-GOES-YOUR-BUILD-HOOK
```

Replace *HERE-GOES-YOUR-BUILD-HOOK* with the build hook url you created in Netlify dashboard. Now site will rebuild every morning, I hope this is useful to you!