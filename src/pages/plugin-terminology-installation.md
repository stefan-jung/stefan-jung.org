---
title: Terminology plugin installation
permalink: /plugins/terminology-installation.html
description: Installation instructions
layout: page
eleventyNavigation:
  key: plugin-terminology-installation
  parent: plugin-terminology
  title: Terminology plugin installation
  excerpt: Installation instructions
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)


Installation
============

Prerequisites
-------------

*   DITA-OT 3.x or DITA-OT 4.x
*   oXygen XML 23 or higher

  

Install the plugin to the DITA-OT
---------------------------------

You can install the plugin from the DITA-OT registry with this command:

```
dita --install org.jung.terminology
```

To install the latest version, which might not yet be published to the DITA-OT registry, use this command:

```
dita --install https://github.com/stefan-jung/org.jung.terminology/archive/main.zip
```

  

Installing the oXygen Framework
---------------------------

The oXygen framework helps you to author your terminology database. It consists of oXygen styles and actions that help you create and edit terms.

1.  In oXygen XML open the menu `Options` > `Preferences`.
2.  In the preferences, open `Document Type Association` > `Locations`.
3.  Add the directory of the plugin. You can find the plugin in the `plugins` directory of the DITA-OT, e.g. `/home/user/workspace/DITA/dita-ot/plugins/org.jung.terminology`.

