---
title: Graal VM plugin
permalink: /plugins/graalvm.html
description: Plugin for using JavaScript with Apache Ant using the Graal VM.
layout: page
eleventyNavigation:
  key: plugin-graal
  parent: plugins
  title: Graal VM plugin
  excerpt: DITA-OT plugin providing the Graal VM for excecuting JavaScript with Apache Ant
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

[org.jung.graal](https://github.com/stefan-jung/org.jung.graal) is a plugin for the [DITA-OT](https://www.dita-ot.org/) and is providing the Graal VM for executing JavaScript with Apache Ant.