---
title: "[Ubuntu] clear read only status issue"
date: "2019-08-07T21:19:12.199Z"
template: "post"
draft: false
slug: "/posts/ubuntu-clear-read-only-status-issues/"
category: "Ubuntu"
tags:
  - "Ubuntu"
  - "Linux"
  - "Read-only-status-issues"
description: "If you're a Ubuntu user and see a clear read only status issue,"
---

<figure>
    <img src="/media/20190807-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

If you're a Ubuntu user and see a clear read only status issue, it has something to do with chown and chmod of Linux authority control command.

Enter following command and your only readable issue will be resolved.

    sudo chown -R yourusername your-project-folder

The **[`chmod`](https://www.unixtutorial.org/commands/chmod)** and [\*\*`chown`](https://www.unixtutorial.org/commands/chown)\*\* commands are used to control access to files in UNIX and Linux systems.

**To simply put:**

- `chown` defines who owns the file.
- `chmod` defines who can do what.

The [chmod command](https://www.unixtutorial.org/commands/chmod) allows changing permissions of files and folders.

The [chown command](https://www.unixtutorial.org/commands/chown) allows changing the owner of a given file or folder, which can be a user and a group or all.

**Ref - [https://askubuntu.com/questions/918379/what-is-the-main-difference-between-chmod-and-chown/918388](https://askubuntu.com/questions/918379/what-is-the-main-difference-between-chmod-and-chown/918388)**

---

> **We are creating wealth every time we write a code**
