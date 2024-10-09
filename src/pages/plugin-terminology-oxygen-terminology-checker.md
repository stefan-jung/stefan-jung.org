---
title: Oxygen Terminology Checker
permalink: /plugins/terminology-oxygen-terminology-checker.html
description: Generate checker rules for the Oxygen Terminology Checker Add-on
layout: page
eleventyNavigation:
  key: plugin-terminology-oxygen-terminology-checker
  parent: plugin-terminology
  title: Oxygen Terminology Checker
  excerpt: Generate checker rules for the Oxygen Terminology Checker Add-on
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

You can generate rules for the [Oxygen Terminology Checker Add-on](https://www.oxygenxml.com/doc/versions/26.1/ug-editor/topics/terminology-checker-addon.html) with the `oxygen-termchecker` transformation.

#### Parameters

The transformation `oxygen-termchecker` allows the following parameters.

`debugging.mode`
: Activates the debugging mode. Possible values are `true` and `false`. Default value is `false`.
 
`include-preferred-terms`
: When preferred terms are included, they will be highlighted by the Oxygen Termchecker and you will see the definition. Possible values are `true` and `false`. Default value is `true`.

`include-admitted-terms`
: When admitted terms are included, they will be highlighted by the Oxygen Termchecker and you will see the definition. Possible values are `true` and `false`. Default value is `true`.