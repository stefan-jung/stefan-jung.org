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