---
title: Terminology Harvester
permalink: /plugins/terminology-harvester.html
description: Harvest new terms from translation memories (.tbx) or XLIFF (.xlf or .xliff) files
layout: page
eleventyNavigation:
  key: plugin-terminology-terminology-harvester
  parent: plugin-terminology
  title: Terminology Harvester
  excerpt: Harvest new terms from translation memories (.tbx) or XLIFF (.xlf or .xliff) files
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

It is always a good idea to maintain and harmonize your translation memories and your terminology database. During this work, you will identify inconsistencies that you can map into your terminology using non-permissible terms and eliminate them in the long term.

The clear solution is of course to prepare a terminological concept before the first translation and to clearly define the associated terms in all target languages. In practice, however, this is often not feasible and often not even desirable for economic reasons.

The Terminology Harvester is crawling through translation memories and XLIFF files and is extracting translated terms as **`<termentry>`** topics, `.csv`, or `.txt` files. The Terminology Harvester intentionally only checks the segments in which the term being searched for occurs exclusively. Segments in which the term is embedded in a sentence structure are deliberately ignored.

![Terminology Harvester principle](../assets/images/termharvester-principle.drawio.png)