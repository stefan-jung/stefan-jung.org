---
title: Terminology plugin
permalink: /plugins/terminology.html
description: Terminology management solution for DITA/Oxygen authoring environments
layout: page
eleventyNavigation:
  key: plugin-terminology
  parent: plugins
  title: Terminology plugin
  excerpt: Terminology management solution for DITA/Oxygen authoring environments
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

{% set crumbs = collections.all | eleventyNavigationBreadcrumb(eleventyNavigation.key) %}
{% for crumb in crumbs %}
Parent: <a class="crumb" href="{{ crumb.url | url }}">{{ crumb.title }}</a>
{% endfor %}

[org.jung.terminology](https://github.com/stefan-jung/org.jung.terminology) is a full-blown terminology management solution for DITA/Oxygen XML authoring environments. Technically speaking it's a plugin for the [Oxygen Publishing Engine](https://www.oxygenxml.com/publishing_engine.html) and the [DITA-OT](http://dita-ot.github.io/). The plugin ships the specialized **`<termentry>`** topic type and a few others. The **`<termentry>`** represents a single terminology concept and contains all metadata and all linguistic information of the terminology concept in all languages.

You can watch the video [DITA terminology management and checking from the DITA-OT Day 2016](https://www.youtube.com/watch?v=WpRsOONVzvE) to get a fundamental understanding of the plugin.


Main Features
=============

* Create and change terms easily using specialized DITA topics. The new DITA `<termentry>` topic represents a single terminology concept. Terminology concepts are linked together to a terminology database using the new DITA `<termmap>` map.
* Author terminology concepts easily using an <oXygen/> XML framework, which is providing author mode stylesheets, which simplify the editing of `<termentry>` and `<termmap>` topics and maps.
* **Termbrowser** - Generate a responsive website for browsing through your terminology. Read more on [Terminology browser](/plugins/termbrowser.html)
* **Oxygen Terminology Checker** - Generate terminology checker rules for the [Oxygen Terminology Checker Add-on](https://www.oxygenxml.com/doc/versions/26.1/ug-editor/topics/terminology-checker-addon.html). Read more on [Oxygen Terminology Checker](/plugins/terminology-oxygen-terminology-checker.html). 
* **Termchecker for DITA and XLIFF** - Check terminology in DITA and XLIFF files with Schematron rules. Read more on [Termchecker for DITA and XLIFF](/plugins/terminology-checker-dita-xliff.html).
* **Terminology Harvester** - Harvest new terms from translation memories (.tmx) or XLIFF files (.xlf or .xliff). Read more on [Terminology Harvester](/plugins/terminology-harvester.html).
* **TBX/MARTIF** - You can generate TermBase eXchange (TBX) files to share your terminology with your translation vendor. Read more on [TermBase eXchange (TBX)/MARTIF](/plugins/terminology-tbx.html).
* **ODS Export/Import** - You can export your terminology in a specific language as an OpenDocument Spreadsheet. This is helpful to localize/review your terminology. Read more on [OpenDocument Spreadsheet (ODS)](/plugins/terminology-ods.html)

Next steps
==========

* **Installation** - If you would like to install the plugin, follow the [installation instructions](/plugins/terminology-installation.html).
* **Using the plugin** - If you would like to start using the plugin, follow the [usage instructions](/plugins/terminology-usage.html).