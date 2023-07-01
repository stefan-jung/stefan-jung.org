---
title: Plugins
permalink: /plugins/index.html
description: Plugins for the DITA-OT
layout: page
eleventyNavigation:
  key: plugins
  title: DITA-OT Plugins
  excerpt: Overview of the provided DITA-OT plugins
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

{{
  collections.all |
  eleventyNavigation |
  eleventyNavigationToHtml({ showExcerpt: true }) |
  safe
}}

