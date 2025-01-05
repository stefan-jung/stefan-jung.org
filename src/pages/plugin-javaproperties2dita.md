---
title: Java Properties 2 DITA plugin
permalink: /plugins/javaproperties2dita.html
description: Plugin for converting Java properties to DITA
layout: page
eleventyNavigation:
  key: plugin-javaProperties2dita
  parent: plugins
  title: Java Properties 2 DITA plugin
  excerpt: DITA-OT plugin for converting Java property files to DITA
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

[org.jung.javaproperties2dita](https://github.com/stefan-jung/org.jung.javaproperties2dita) is a DITA-OT plugin for converting Java property files to DITA. Java property files are simple key-value-files, that are converted to DITA `<keyword>` elements. If you have found a bug or want to request a feature, please raise an [issue](https://github.com/stefan-jung/org.jung.javaproperties2dita/issues).

  

**Input**

```xml
key=value
```

**Output**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "topic.dtd">
<topic id="test.properties">
    <title>test.properties</title>
    <body>
        <div>
            <keyword id="key">value</keyword>
        </div>
    </body>
</topic>
```

Installation
============

Installing the Plugin
----------------------

Install the plugin to the DITA-OT with the following command:

```xml
dita --install https://github.com/doctales/org.doctales.javaProperties2Dita/archive/master.zip
```

  

Installing the Framework
------------------------

This step is optional. To install the <oXygen/> XML framework, proceed as follows:

1.  In <oXygen/> open the menu `Options` > `Preferences`.
2.  In the preferences, open `Document Type Association` > `Locations`.
3.  Add the directory of the plugin in the DITA-OT, e.g. `/home/user/workspace/dita-ot/plugins/org.doctales.javaProperties2Dita`.

Using the Plugin
================

Convert via <oXygen/> transformation scenario
---------------------------------------------

1.  Open a Java properties file in <oXygen/>.
2.  Launch the transformation sceanrio `Convert Java-Properties 2 DITA`. A DITA file is created in the directory of the input file.

Convert via Apache Ant transformation scenario
----------------------------------------------

1.  Import the `build_javaProperties2Dita.xml` to your Apache Ant build file.
2.  Call the transformation using the custom `<convert-properties-to-dita>` element.
    
    ```xml
    <convert-properties-to-dita input="input.properties" output="output.dita"/>
    ```
