---
title: Ant Contrib plugin
permalink: /plugins/ant-contrib.html
description: Plugin providing the ant-contrib library for Apache Ant.
layout: page
eleventyNavigation:
  key: plugin-ant-contrib
  parent: plugins
  title: Ant Contrib plugin
  excerpt: DITA-OT plugin providing the *ant-contrib* library for Apache Ant
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

[org.jung.ant-contrib](https://github.com/stefan-jung/org.jung.ant-contrib) is a plugin for the [DITA-OT](https://www.dita-ot.org/) and is providing the *ant-contrib* library for Apache Ant.


Installation
============

You can install the plugin from the DITA-OT registry with the following command:

```
dita --install org.jung.ant-contrib
```

You can also install the plugin from GitHub with the following command:

```
dita --install https://github.com/stefan-jung/org.jung.ant-contrib/archive/master.zip
```

Usage
=====

To use the Ant-Contrib plug-in simply add a `<require>` element to the [plugin descriptor file](https://www.dita-ot.org/dev/topics/plugin-configfile#plugin-configfile__plugin-sample) `plugin.xml` of your own DITA-OT plugin.

```xml
<plugin id="com.example.dita">
  <require plugin="org.jung.ant-contrib"/>
</plugin>
```


License
=======

Apache 2.0 ©2024 Stefan Jung

The Program includes the following additional software components which were obtained under license:

[ant-contrib.jar](http://ant-contrib.sourceforge.net/) - Apache 2.0 license
