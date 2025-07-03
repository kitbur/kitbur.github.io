---
title: "Chroma Botanica"
date: 2025-06-09
description: "A modern, single-page art portfolio enhanced with a powerful, data-driven architecture, enabling complete site customization for my non-technical client solely through HTML."
image: "/images/projects/chroma-botanica.webp"
link: "https://kitbur.github.io/chroma-botanica/"
repo: "https://github.com/kitbur/chroma-botanica"
tech:
  - "JavaScript"
  - "jQuery"
  - "HTML"
  - "CSS"
---

Chroma Botanica is a beautiful, one-page art portfolio that was commissioned by a client. 

The core challenge of this project was to empower a non-technical user to manage all site content without ever editing a line of CSS or JavaScript.

## Declarative, HTML-First Architecture

This project features a declarative content management system. All dynamic elements—including slideshow images, section backgrounds, and gallery content are controlled via custom HTML `data-` attributes, powered by JavaScript. This architecture centralizes content updates within the `index.html` file, providing easy customization for the end-user.

## Intelligent Slideshow Module

A custom slideshow module (`slideshow.js`) was engineered to provide a more engaging user experience than a standard sequential rotator. The script uses a "least viewed" algorithm to track image impressions, ensuring a more varied and non-repetitive presentation of slides. This smart rotation logic is paired with user-focused features, including navigation dots and pause-on-hover interactivity.

## Dynamic Gallery Captions

To add more value to the portfolio gallery, the Poptrox modal was extended to support social media links. A custom `caption` function parses a JSON array passed via a `data-caption-icons` attribute, dynamically generating and appending clickable Font Awesome icons to the caption for each image. This allows each art piece to link to multiple external sources, configured entirely within the HTML.