---
title: Schematron plugin
permalink: /plugins/schematron.html
description: Plugin for using Schematron with the DITA-OT
layout: page
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[org.doctales.schematron](https://github.com/doctales/org.doctales.schematron) is a DITA-OT plugin for validating DITA-XML files with Schematron. This plugins is based on [ph-schematron](https://github.com/phax/ph-schematron).

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

<table class="wrapped confluenceTable"><colgroup><col><col><col></colgroup><tbody><tr><th class="confluenceTh">Parameter</th><th colspan="1" class="confluenceTh">Values</th><th class="confluenceTh">Description</th></tr><tr><td colspan="1" class="confluenceTd"><div class="content-wrapper"><p class="auto-cursor-target"><code>schematron.processing.engine</code></p></div></td><td colspan="1" class="confluenceTd"><p>"<code>schematron</code>", "<code>xslt</code>", "<code>pure</code>"</p><p><strong>Default</strong>: <code>pure</code></p></td><td colspan="1" class="confluenceTd">Engine used to validate DITA maps and topics</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.map.validation.files</pre></td><td colspan="1" class="confluenceTd"><p><br></p></td><td colspan="1" class="confluenceTd">Comma separated list of Schematron files for map validation</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.topic.validation.files</pre></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd">Comma separated list of Schematron files for topic validation</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.fail</pre></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd">Indicates, whether the build should fail, if a role fires with a certain role level.</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.failon.fatal</pre></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd">Indicates, whether the build should fail, if a Schematron rule with role '<code>fatal</code>' is fired.</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.failon.error</pre></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd">Indicates, whether the build should fail, if a Schematron rule with role '<code>error</code>' is fired.</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.failon.warning</pre></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd">Indicates, whether the build should fail, if a Schematron rule with role '<code>warning</code>' is fired.</td></tr><tr><td colspan="1" class="confluenceTd"><pre>schematron.failon.info</pre></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd">Indicates, whether the build should fail, if a Schematron rule with role '<code>info</code>' is fired.</td></tr></tbody></table>