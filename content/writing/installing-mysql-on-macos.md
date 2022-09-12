---
comments: true
date: "2020-10-23T00:00:00Z"
description: Here's how to find and download MySQL for macOS
published: true
summary: Here's how to find and download MySQL for macOS
categories:
- article
tags:
- mysql
title: Installing MySQL on MacOS
---

Here's how to find and download MySQL for macOS.

## Installation

1. Go to the [MySQL website](https://dev.mysql.com/downloads/mysql/) and download the disk image (.dmg).
2. Double-click the file to mount the disk image and see its contents.
3. Double-click the MySQL installer package from the disk. It is named according to the version of MySQL you have downloaded.
4. The initial wizard introduction screen references the MySQL server version to install. Click `Continue` to begin the installation.
5. From the `Installation Type` page you can either click Install to execute the installation wizard using all defaults, click `Customize` to alter which components to install (MySQL server, Preference Pane, Launchd Support -- all enabled by default).
6. Click `Install` to begin the installation process.
7. Enter your password and click `Install Software`.
8. Wait while the files copy to your Mac.
9. `Summary` is the final step and references a successful and complete MySQL Server installation.

MySQL server is now installed, but it is not loaded (or started) by default. Use either launchctl from the command line, or start MySQL by clicking `Start` using the MySQL preference pane.

## Launch MySQL server

1. Go to `System Preferences` on your Mac.
2. Click MySQL to launch it.
3. Click the `Start MySQL Server` button to start and stop the server.
4. Click the `Configuration` tab to set advanced options.
5. Click `Apply`.