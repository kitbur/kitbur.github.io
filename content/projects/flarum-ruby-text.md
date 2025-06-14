---
title: "Flarum Ruby Text Extension"
date: 2025-06-08
description: "A Flarum extension that adds ruby text annotations to forum posts via BBCode. "
image: "/images/projects/flarum-ruby-text.webp"
link: ""
repo: "https://github.com/kitbur/ruby-text"
tech:
  - "Node.js"
  - "PHP"
  - "nginx"
  - "Docker"
  - "Composer"
  - "MariaDB"
  - "Mithril.js"
  - "Laravel"
  - "Webpack"
  - "Git"
---

A client requested a Flarum extension to add support for ruby text, a typographic feature essential for phonetic annotations in certain languages. While the extension's core logic was straightforward, the real challenge was building a modern development environment.

My initial local Flarum installation was unstable, so I turned to Docker for a cleaner setup. I immediately hit a major roadblock: the Docker image recommended by Flarum was for version 1.3, while the latest stable release was 1.8. This wasn't just a minor version gap; Flarum 1.4 and newer require a version of PHP that the official image didn't support.

To solve this, I [forked the reccomended Docker image](https://github.com/kitbur/docker-flarum) and heavily modified it to run the latest versions of PHP and Composer. This created a new, modern Flarum development environment compatible with both version 1.8 and the upcoming 2.0 release.

With a stable environment finally in place, I was able to write, test, and deliver my extension to my happy client, and contribute a valuble tool  the extension, deliver tool to the Flarum community.