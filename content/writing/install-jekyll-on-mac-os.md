---
date: "2018-06-14T00:00:00Z"
description: How to install Jekyll using Homebrew
summary: How to install Jekyll using Homebrew.
categories:
- article
tags:
- jekyll
title: Install Jekyll on Mac OS
---

Jekyll is a simple, blog-aware, static site generator perfect for personal, project, or organization sites. Think of it like a file-based CMS, without all the complexity. Jekyll takes your content, renders Markdown and Liquid templates, and spits out a complete, static website ready to be served by Apache, Nginx or another web server. 

1. Open up the Terminal. We need to install “Command Line Tools” which gives us access to commonly used tools, utilities, and compilers: 
```bash
xcode-select --install
```
2. Run the command below or open up Xcode which will prompt you to agree to the license:
```bash
sudo xcodebuild -license
```
3. Install Homebrew:
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
4. Install Ruby:
```bash
brew install ruby
```
5. Install Jekyll:
```bash
sudo gem install jekyll
```
6. Check the version installed:
```bash
jekyll -v
```
7. Create a new Jekyll site at ```./site```
```bash
jekyll new site
```
8. Change into your new directory:
```bash
cd site
```
9. Build the site and make it available on a local server:
```bash
bundle exec jekyll serve
```
10. Now browse to [http://localhost:4000](http://localhost:4000)

Jekyll themes may require certain Ruby gem dependencies. These dependencies are stored in a Gemfile, which is packaged with the Jekyll theme. You can install these dependencies through Bundler:
```bash
gem install bundler
```
