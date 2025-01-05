---
title: Schematron plugin
permalink: /plugins/schematron.html
description: Plugin for using Schematron with the DITA-OT
layout: page
eleventyNavigation:
  key: plugin-schematron
  parent: plugins
  title: Schematron plugin
  excerpt: DITA-OT plugin for validating DITA-XML files with Schematron
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

[org.jung.schematron](https://github.com/stefan-jung/org.jung.schematron) is a DITA-OT plugin for validating DITA-XML files with Schematron. This plugins is based on [ph-schematron](https://github.com/phax/ph-schematron).

Installing the Plugin
=====================

1.  Move to the `~/bin` directory of the DITA-OT.
2.  Install the plugin using the dita command.
    
    ```xml
    dita --install https://github.com/doctales/org.doctales.schematron/archive/master.zip
    ```
    

Using the Plugin
================

You need to either set the '`schematron.map.validation.files`' and/or '`schematron.map.validation.files`' property. The validation is then triggered automatically after the DITA-OT preprocessing phase.

Parameters
==========


`schematron.processing.engine`
: Engine used to validate DITA maps and topics. Possible values are `schematron`, `xslt`, `pure`. Default value is `pure`.

`schematron.map.validation.files`
: Comma separated list of Schematron files for map validation.

`schematron.topic.validation.files`
: Comma separated list of Schematron files for topic validation

`schematron.fail`
: Indicates, whether the build should fail, if a role fires with a certain role level. Possible values are `true` or `false`. Default value is `true`.

`schematron.failon.fatal`
: Indicates, whether the build should fail, if a Schematron rule with role `fatal` is fired. Possible values are `true` or `false`. Default value is `true`.

`schematron.failon.error`
: `true` or `false` Default: `true` Indicates, whether the build should fail, if a Schematron rule with role `error` is fired. Possible values are `true` or `false`. Default value is `true`.

`schematron.failon.warning`
: `true` or `false` Default: `false` Indicates, whether the build should fail, if a Schematron rule with role `warning` is fired. Possible values are `true` or `false`. Default value is `false`.

`schematron.failon.info`
: `true` or `false` Default: `false` Indicates, whether the build should fail, if a Schematron rule with role `info` is fired. Possible values are `true` or `false`. Default value is `false`.