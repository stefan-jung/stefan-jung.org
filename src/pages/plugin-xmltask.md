---
title: XML Task plugin
permalink: /plugins/xmltask.html
description: Plugin for using the OOPS consultancy XML Task with Apache Ant.
layout: page
eleventyNavigation:
  key: plugin-xmltask
  parent: plugins
  title: XMLTask plugin
  excerpt: Plugin for the DITA-OT and is providing the OOPS Consultancy XML ask for Apache Ant
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

[org.jung.xmltask](https://github.com/stefan-jung/org.jung.xmltask) is a plugin for the [DITA-OT](https://www.dita-ot.org/) and is providing the [OOPS Consultancy XML Task](http://www.oopsconsultancy.com/software/xmltask/) for Apache Ant.
