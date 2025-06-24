---
title: "Flarum Ruby Text Extension"
date: 2025-06-08
description: "A DevOps and extension development project that involved architecting a modern, containerized Flarum environment to deliver a critical typography feature for a client."
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

This project began with a client request for a custom Flarum extension to support ruby text, a feature essential for phonetic annotations in certain languages. Successful delivery required a significant DevOps initiative to first modernize the development environment before the feature itself could be built.
The Technical Blocker

Upon initiating the project, it became clear that the officially recommended Docker tooling was several versions behind Flarum's stable release. This created a critical dependency conflict, making it impossible to build or test extensions against the latest version of the platform, as the environment lacked support for the required versions of PHP and Composer.

## DevOps Modernization

To unblock development, I engineered a new, modern Flarum development environment and then delivered the client's feature. I [forked the reccomended Docker image](https://github.com/kitbur/docker-flarum) and re-architected it to run the latest versions of PHP and Composer. This created a stable, containerized platform compatible with both the current (1.8) and upcoming (2.0) releases of Flarum.

## Feature Delivery

With a reliable environment in place, I developed, tested, and delivered the requested ruby text extension to the client, successfully fulfilling their business requirement.

## Open-Source Contribution
    
Recognizing this solution would benefit other developers, I published the modernized Docker image publicly, contributing a valuable and up-to-date tool to the Flarum community.