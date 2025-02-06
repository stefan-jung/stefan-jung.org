---
title: OpenDocument Spreadsheet (ODS)
permalink: /plugins/terminology-ods.html
description: Export your terminology to an ODS file and import it after localization/review
layout: page
eleventyNavigation:
  key: plugin-terminology-ods
  parent: plugin-terminology
  title: OpenDocument Spreadsheet (ODS)
  excerpt: Export your terminology to an ODS file and import it after localization/review
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

OpenDocument Spreadsheet (ODS) is a spreadsheet format, but technically simpler than XSLX. You can export your terminology in a specific language, modify the spreadsheet and then import it again afterwards. This is very helpful, if you would like to add a completely new language to your terminology, or if you would like to review the existing terms in a specific language.

Usage
-----

Open the **`<termmap>`** in Oxygen XML and call the `Export OpenDocument Spreadsheet (ODS)` from the `Terminology` menu. You can later import the same file again by calling `Import OpenDocument Spreadsheet (ODS)` from the `Terminology` menu.