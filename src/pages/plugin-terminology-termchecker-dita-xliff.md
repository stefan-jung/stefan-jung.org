---
title: Terminology Checker for DITA and XLIFF
permalink: /plugins/terminology-checker-dita-xliff.html
description: Schematron rules for checking terminology in DITA and XLIFF files
layout: page
eleventyNavigation:
  key: plugin-terminology-checker-dita-xliff
  parent: plugin-terminology
  title: Terminology Checker for DITA and XLIFF
  excerpt: Schematron rules for checking terminology in DITA and XLIFF files
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

You can search for not recommended terms in DITA and XLIFF files with Schematron rules. You can generate them with the  with the `termchecker-dita` and `termchecker-xliff` transformations. These Schematron rules suggest corresponding preferred synonyms.

> **NOTE** You can create an Oxygen validation scenario to perform these checks automatically.
> 

Termchecker DITA
---------------

The transformation `termchecker-dita` generates Schematron rules for DITA topics.


#### Parameters

`debugging.mode`
: Activates the debugging mode. Possible values are `true` and `false`. Default value is `false`.

`args.language`
: Language of the terminology check rules, for instance `en-US`.


Termchecker XLIFF
----------------


#### Parameters

`debugging.mode`
: Activates the debugging mode. Possible values are `true` and `false`. Default value is `false`.

`args.check.elements`
: Choose whether terms should be checked only in source elements or target elements or in both of them.

`args.language`
: Language of the terminology check rules.


