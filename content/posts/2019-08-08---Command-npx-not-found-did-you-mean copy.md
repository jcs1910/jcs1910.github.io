---
title: "[NPX] Unable to install npx?"
date: "2019-08-09T15:15:32.199Z"
template: "post"
draft: false
slug: "/posts/Command-npx-not-found-did-you-mean/"
category: "HTTP"
tags:
  - "NPX"
  - "Ubuntu"
  - "window"
  - "npm"

description: "Command 'npx' not found, did you mean"
---

<figure>
    <img src="/media/20190809-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

Unable to install npx, you might need to install npx globally. This is because NPX should come with npm 5.2+ and Windows might not download npx. That's why you're seeing the below message.

    Command 'npx' not found, did you mean:

      command 'upx' from snap upx (v0.2.3)
      command 'nex' from deb nvi
      command 'np' from deb mosquitto-auth-plugin
      command 'nyx' from deb nyx
      command 'gpx' from deb gpx
      command 'npm' from deb npm

    See 'snap info <snapname>' for additional versions.

## Solution

If you're window user, enter `npm i -g npx` in command

If you're Linux user, enter `npm i -g npx` in terminal

Then, install `npx create-react-app [your folderName]`

---

> **We are creating wealth every time we write a code**
