---
title: Terminology plugin
permalink: /plugins/terminology.html
description: Plugin for managing terminology with DITA
layout: page
eleventyNavigation:
  key: plugin-terminology
  parent: plugins
  title: Terminology plugin
  excerpt: DITA-OT plugin for creating a DITA-based terminology database
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

[org.doctales.terminology](https://github.com/doctales/org.doctales.terminology) is a plugin for the [DITA-OT](http://dita-ot.github.io/) for creating a DITA-based terminology database. This site should help you to get started. If you have a question, go to the [questions](https://doctales.atlassian.net/wiki/display/TERM/questions/all) section and ask the DOCTALES team or join our [#terminology](https://doctales.slack.com/) Slack channel. If you have found a bug or want to request a feature, please raise an [issue](https://github.com/doctales/org.doctales.terminology/issues).

  

**Quick Start Presentation**: Recorded by [Syncro Soft/OxygenXML Editor](https://www.oxygenxml.com/about_us.html), DITA-OT Day 2016, Munich

Slides: [https://doctales.github.io/presentations/presentation-dita-ot-day/index.html](https://doctales.github.io/presentations/presentation-dita-ot-day/index.html)

  

  

Features
========

*   Create and change terms easily using specialized DITA topics. The new DITA `<termentry>` topic represents a single term. Terms are linked together to a terminology database using the `<termmap>` map.
*   Author terms easily using an <oXygen/> XML framework with author mode stylesheets, that simplify the editing of `<termentry>` and `<termmap>` topics.

  

Termbrowser
-----------

Termbrowser are designed to browse through your terminology database.

*   [Termbrowser Classic](/wiki/spaces/DOC/pages/40009112/Termbrowser+Classic) — The DITA Termbrowser Classic (format: `termbrowser-classic`) is a frame-based website for browsing through your terminology database.
    
*   [Termbrowser HTML5](/wiki/spaces/DOC/pages/40009067/Termbrowser+HTML5) — The DITA Termbrowser HTML5 is based on the plugin **org.dita.html5**, that is shipped with the DITA-OT. Use this termbrowser, if you don't want to rely on the proprietary **com.oxygenxml.webhelp** termbrowser. This is, for example, recommended, if you plan to build your termbrowser in a Continuous Deployment Pipeline. The **com.oxygenxml.webhelp** transformation scenario requires an expensive server license to do that.
    
*   [Termbrowser Responsive](/wiki/spaces/DOC/pages/40008984/Termbrowser+Responsive) — The DITA Termbrowser Responsive (format: `termbrowser-reponsive`) is a reponsive website for browsing through your terminology database.
    

  

Termchecker
-----------

Termchecker are designed to search for not recommended terms in various data formats.

*   [Termchecker XLIFF](/wiki/spaces/DOC/pages/40008144/Termchecker+XLIFF) — This page explains how to use the termchecker for XLIFF. The Termchecker XLIFF (as the [Termchecker DITA](/wiki/spaces/DOC/pages/40008098/Termchecker+DITA)) is technically a [Schematron](http://www.schematron.com/) file, that searches for not recommended terms and replaces them with preferred synonyms. It is recommended [add a new document type association](http://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/preferences-document-type-association.html) by extending the `XLIFF` framework and [create a new validatation scenario](https://www.oxygenxml.com/doc/versions/18/ug-editor/tasks/create-validation-scenario.html) using the termchecker XLIFF Schematron file.
    
*   [Termchecker DITA](/wiki/spaces/DOC/pages/40008098/Termchecker+DITA) — This page explains how to use the termchecker for DITA. The DITA Termchecker is technically a [Schematron](http://www.schematron.com/) file, that searches for not recommended terms and replaces them with preferred synonyms. It is recommended [add a new document type association](http://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/preferences-document-type-association.html) by extending the `DITA` framework and [create a new validatation scenario](https://www.oxygenxml.com/doc/versions/18/ug-editor/tasks/create-validation-scenario.html) using the termchecker DITA Schematron file.
    

  

TBX
---

TBX is a data format to exchange a terminology database, e.g. to pass it to your Language Service Provider (LSP).

*   [TBX-Basic](/wiki/spaces/DOC/pages/40008215/TBX-Basic) — The transformation scenario `TBX-Basic` transforms the terminology to a [TBX-Basic](http://www.ttt.org/oscarstandards/tbx/tbx-basic.html) file. A TBX-Basic file is a lighter version of the Terminology Base Exchange (TBX) format. You can send this file to a language service provider to make sure, that the translator uses the correct terminology during translation.
    
*   [TBX-Min](/wiki/spaces/DOC/pages/40008179/TBX-Min) — The transformation scenarios `TBX-Min` transforms the terminology to a TBX-Min file. The TBX-Min format is a dialect of the TermBase eXchange (TBX) format and is designed for bilingual or monolingual glossaries. You can use TBX-Min to transmit a terminology database to a language service provider (LSP). You can send this file to a language service provider to make sure, that the translator uses the correct terminology during translation. The TBX-Min format is explained in the paper [TBX - Min: A Simplified TBX - Based Approach to Representing Bilingual Glossaries](http://www.tbxinfo.net/wp-content/uploads/2016/10/lommel_melby_glenn_hayes_snow-final.pdf).
    

  

Installation
============

Prerequisites
-------------

*   DITA-OT 2.3.x, DITA-OT 2.4.x, DITA-OT 2.5.x or DITA 3.x
*   <oXygen/> XML 19 or higher (optional)

  

Install the plugin to the DITA-OT
---------------------------------

You can install the plugin to the DITA-OT with a single command:

```xml
dita --install https://github.com/doctales/org.doctales.terminology/archive/master.zip
```

  

Installing the oXygen Framework
---------------------------

The oXygen framework helps you to author your terminology database. It consists of oXygen styles and actions that help you create and edit terms.

1.  In <oXygen/> open the menu `Options` > `Preferences`.
2.  In the preferences, open `Document Type Association` > `Locations`.
3.  Add the directory of the plugin, e.g. `/home/user/workspace/DITA/dita-ot/plugins/org.doctales.terminology`.

  

Using the plugin
================

**org.doctales.terminology** ships a few sample files, that show you how to create terms and create the various outputs. To test the transformations, just open the `terminology.ditamap` in the oXygen DITA Maps Manager and run a transformation scenario.


This page explains how to use the termchecker for DITA. The DITA Termchecker is technically a [Schematron](http://www.schematron.com/) file, that searches for not recommended terms and replaces them with preferred synonyms. It is recommended [add a new document type association](http://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/preferences-document-type-association.html) by extending the `DITA` framework and [create a new validatation scenario](https://www.oxygenxml.com/doc/versions/18/ug-editor/tasks/create-validation-scenario.html) using the termchecker DITA Schematron file.

**Table of Contents**

/\*<!\[CDATA\[\*/ div.rbtoc1687809294174 {padding: 0px;} div.rbtoc1687809294174 ul {list-style: disc;margin-left: 0px;} div.rbtoc1687809294174 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Parameters](#TermcheckerDITA-Parameters)
*   [Publishing a Termchecker for DITA using the dita command](#TermcheckerDITA-PublishingaTermcheckerforDITAusingtheditacommand)
*   [Publishing a Termchecker for DITA from oXygen XML](#TermcheckerDITA-PublishingaTermcheckerforDITAfromoXygenXML)

#### Parameters

The termchecker for DITA transformation supports the following parameters, that can be passed with `-Dparameter=value` to the dita command. You can find more information about parameters on [Building output using the dita command](http://www.dita-ot.org/dev/user-guide/build-using-dita-command.html).

| Parameter       | Values  | Description                             |
|-----------------|---------|-----------------------------------------|
| `args.language` | `de-DE` | Language of the terminology check rules |


#### Publishing a Termchecker for DITA using the dita command

You can find more information about the dita command on [Building output using the dita command](http://www.dita-ot.org/dev/user-guide/build-using-dita-command.html).

  

**Example**

```xml
dita --input terminology.ditamap --format termchecker-dita -Dargs.language=en-GB --output termchecker-dita
```

#### Publishing a Termchecker for DITA from oXygen XML

1.  Open the samples DITA map `~/org.doctales.terminology/samples/terminology.ditamap` in the <oXygen/> DITA Maps Manager.
2.  In the `Transformation Scenarios` view, double click the entry `Termchecker for DITA`.  
    ![](attachments/40008098/40009202.png)  
      
    The terminology is transformed to the Schematron file `~/out/termchecker-dita/terminology-DITA-en-GB.sch`. By default, the terminology checker is generated for British English (`en-GB`). If you want to generate the terminology checker for another language, you have to change the parameter `args.language` of the transformation scenario.
3.  Create a new DITA validation scenario and refer to the generated Schematron file.
    1.  In <oXygen/> open the menu `Options` > `Preferences`.
    2.  In the `Document Type Association` menu, select the `DITA` document type association and click the button`Edit`.
    3.  Open the `Validation` tab and click the + button, to create a new validation scenario.
    4.  Create a new validation scenario named `Terminology` and specify the Schematron schema.  
        ![](attachments/40008098/40009206.png)  
        ![](attachments/40008098/40009213.png)  
        ![](attachments/40008098/40009219.png)  
          
        
4.  Create a new DITA topic.
5.  Set the `xml:lang` attribute of the topic to `en-GB` and write the word `truck` somewhere in the topic.  
    The term violation is indicated with a small lamp icon ![](attachments/40008098/40009225.png). Click on the lamp select the `Replace with an allowed term`action. This works both in text and in author mode.  
    ![](attachments/40008098/40009231.gif)  
    ![](attachments/40008098/40009239.gif)  
      
    The deprecated term has been replaced.

**Explanation**

The deprecated and the allowed term notations are defined in the `truck.dita` file.

```xml
<fullForm usage="notRecommended" language="en-GB">
  <termVariant>truck</termVariant>
</fullForm>
<fullForm usage="preferred" language="en-GB">
  <termVariant>lorry</termVariant>
</fullForm>
```


This page explains how to use the termchecker for XLIFF. The Termchecker XLIFF (as the [Termchecker DITA](Termchecker-DITA_40008098.html)) is technically a [Schematron](http://www.schematron.com/) file, that searches for not recommended terms and replaces them with preferred synonyms. It is recommended [add a new document type association](http://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/preferences-document-type-association.html) by extending the `XLIFF` framework and [create a new validatation scenario](https://www.oxygenxml.com/doc/versions/18/ug-editor/tasks/create-validation-scenario.html) using the termchecker XLIFF Schematron file.

**Table of Contents**

/\*<!\[CDATA\[\*/ div.rbtoc1687809295943 {padding: 0px;} div.rbtoc1687809295943 ul {list-style: disc;margin-left: 0px;} div.rbtoc1687809295943 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Parameters](#TermcheckerXLIFF-Parameters)

#### Parameters

| Parameter             | Values                                       | Description                                                                                          |
|-----------------------|----------------------------------------------|------------------------------------------------------------------------------------------------------|
| `args.check.elements` | `source`, `target`, `both` Default: `source` | Choose whether terms should be checked only in source elements or target elements or in both of them |
| `args.language`       | Example: `de-DE`                             | Language of the terminology check rules                                                              |


The DITA Termbrowser Responsive (format: `termbrowser-reponsive`) is a reponsive website for browsing through your terminology database.

**Table of Contents**

/\*<!\[CDATA\[\*/ div.rbtoc1687809295977 {padding: 0px;} div.rbtoc1687809295977 ul {list-style: disc;margin-left: 0px;} div.rbtoc1687809295977 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Prerequisites](#TermbrowserResponsive-Prerequisites)
*   [Parameters](#TermbrowserResponsive-Parameters)
*   [Example](#TermbrowserResponsive-Example)

  

The _termbrowser responsive_ is based on the <oXygen/> plugin **com.oxygenxml.webhelp.responsive** (**com.oxygenxml.webhelp** before <oXygen/> 19.1) and is used to browse through the terminology database.

#### Prerequisites

To publish the _termbrowser responsive_, you need to have the plugins **com.oxygenxml.webhelp.responsive** and **com.oxygenxml.webhelp.common** (since <oXygen/> 19.1) or **com.oxygenxml.webhelp** (<oXygen/> 19.0 and earlier) installed to your DITA-OT.

  

If you want to publish the _termbrowser responsive_ via command line interface, you need an additional license, see [Buy Oxygen XML WebHelp](https://www.oxygenxml.com/xml_webhelp/buy_oxygen_xml_webhelp.html).

  

  

#### Parameters

<table class="wrapped confluenceTable"><colgroup><col><col><col></colgroup><tbody><tr><th class="confluenceTh">Parameter</th><th class="confluenceTh">Values</th><th class="confluenceTh">Description</th></tr><tr><td colspan="1" class="confluenceTd"><div class="content-wrapper"><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl"><pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: xml; gutter: false; theme: Eclipse" data-theme="Eclipse">args.default.language</pre></div></div></div></td><td colspan="1" class="confluenceTd"><p><strong>Example</strong>: <code>en-GB</code></p></td><td colspan="1" class="confluenceTd">Language used to generate the termbrowser labels.</td></tr><tr><td class="confluenceTd"><div class="content-wrapper"><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl"><pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: xml; gutter: false; theme: Eclipse" data-theme="Eclipse">args.termstats</pre></div></div></div></td><td class="confluenceTd"><div class="content-wrapper"><strong>Example</strong>: <code>../termstats.xml</code></div></td><td class="confluenceTd">Relative path to the terminology statistics (<code>termstats.xml</code> file). The <code>termstats.xml</code> file is automatically generated with each termbrowser publication. If you pass the <code>termstats.xml</code> from the previous build with this parameter, you can generate a&nbsp;chronological sequence of your terminology metadata.</td></tr></tbody></table>

#### Example

```xml
dita --input terminology.ditamap --format termbrowser-responsive -Dargs.default.language=en-GB --output out/termbrowser-responsive
```


The transformation scenarios `TBX-Min` transforms the terminology to a TBX-Min file. The TBX-Min format is a dialect of the TermBase eXchange (TBX) format and is designed for bilingual or monolingual glossaries. You can use TBX-Min to transmit a terminology database to a language service provider (LSP). You can send this file to a language service provider to make sure, that the translator uses the correct terminology during translation. The TBX-Min format is explained in the paper [TBX - Min: A Simplified TBX - Based Approach to Representing Bilingual Glossaries](http://www.tbxinfo.net/wp-content/uploads/2016/10/lommel_melby_glenn_hayes_snow-final.pdf).

<table class="wrapped confluenceTable"><colgroup><col><col><col></colgroup><tbody><tr><th class="confluenceTh">Parameter</th><th class="confluenceTh">Values</th><th class="confluenceTh">Description</th></tr><tr><td class="confluenceTd"><div class="content-wrapper"><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl"><pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: xml; gutter: false; theme: Eclipse" data-theme="Eclipse">args.source.language</pre></div></div></div></td><td class="confluenceTd"><strong>Example</strong>: <code>de-DE</code> (German/Germany)</td><td class="confluenceTd">Source language of terminology</td></tr><tr><td colspan="1" class="confluenceTd"><div class="content-wrapper"><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl"><pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: xml; gutter: false; theme: Eclipse" data-theme="Eclipse">args.target.language</pre></div></div></div></td><td colspan="1" class="confluenceTd"><strong>Example</strong>: <code>en-GB</code> (English/Great Britain)</td><td colspan="1" class="confluenceTd">Target language of terminology</td></tr></tbody></table>


The transformation scenario `TBX-Basic` transforms the terminology to a [TBX-Basic](http://www.ttt.org/oscarstandards/tbx/tbx-basic.html) file. A TBX-Basic file is a lighter version of the Terminology Base Exchange (TBX) format. You can send this file to a language service provider to make sure, that the translator uses the correct terminology during translation.

**Table of Contents**

/\*<!\[CDATA\[\*/ div.rbtoc1687809296096 {padding: 0px;} div.rbtoc1687809296096 ul {list-style: disc;margin-left: 0px;} div.rbtoc1687809296096 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Parameters](#TBX-Basic-Parameters)

  

#### Parameters

<table class="wrapped confluenceTable"><colgroup><col><col><col></colgroup><tbody><tr><th class="confluenceTh">Parameter</th><th class="confluenceTh">Values</th><th class="confluenceTh">Description</th></tr><tr><td class="confluenceTd"><div class="content-wrapper"><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl"><pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: xml; gutter: false; theme: Eclipse" data-theme="Eclipse">args.source.language</pre></div></div></div></td><td class="confluenceTd"><div class="content-wrapper"><strong>Example</strong>: <code>de-DE</code></div></td><td class="confluenceTd">The source language of the terms.</td></tr><tr><td colspan="1" class="confluenceTd"><div class="content-wrapper"><div class="code panel pdl" style="border-width: 1px;"><div class="codeContent panelContent pdl"><pre class="syntaxhighlighter-pre" data-syntaxhighlighter-params="brush: xml; gutter: false; theme: Eclipse" data-theme="Eclipse">args.target.language</pre></div></div></div></td><td colspan="1" class="confluenceTd"><div class="content-wrapper"><strong>Example</strong>: <code>de-DE</code></div></td><td colspan="1" class="confluenceTd">The target language of the terms.</td></tr></tbody></table>