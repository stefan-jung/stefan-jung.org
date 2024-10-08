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

Creating a **`<termentry>`** topic is as easy as creating a normal DITA topic. The plugin ships also a comprehensive Oxygen XML framework for authoring. The following picture shows, how a **`<termentry>`** topic is rendered in the Oxygen XML Author view.

![Termentry topic in Oxygen XML author view](../assets/images/termentry.png)

+++ **Example:** car.dita **`<termentry>`** topic
```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="urn:jung:dita:rng:termentry.rng" schematypens="http://relaxng.org/ns/structure/1.0"?>
<?xml-model href="urn:jung:dita:rng:termentry.rng" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<termentry id="car">
 <title>Car</title>
 <definition>
  <definitionText>A car is a wheeled, self-powered motor vehicle used for transportation.</definitionText>
  <definitionSource>
   <sourceReference href="https://en.wikipedia.org/wiki/Car" format="html" scope="external"
    >Wikipedia</sourceReference>
  </definitionSource>
 </definition>
 <termBody>
  <fig>
   <title>2015 Volkswagen Passat (3G MY16) 132TSI</title>
   <image href="https://upload.wikimedia.org/wikipedia/commons/7/78/2015_Volkswagen_Passat_%283G_MY16%29_132TSI_station_wagon_%282015-11-11%29_01.jpg" scope="external" width="600px">
    <alt>By OSX (Own work) [Public domain], via Wikimedia Commons</alt>
   </image>
  </fig>
  <domains>
   <domain concept-domain="Car"/>
  </domains>
  <partOfSpeech/>
  <fullForm usage="preferred" language="en-GB">
   <termVariant xml:lang="en-GB">car</termVariant>
  </fullForm>
  <fullForm usage="notRecommended" language="de-DE">
   <termVariant xml:lang="de-DE">Automobil</termVariant>
  </fullForm>
  <abbreviation usage="preferred" language="de-DE">
   <termVariant xml:lang="de-DE">Auto</termVariant>
  </abbreviation>
 </termBody>
 <relations>
  <relatedTerms>
   <relatedTerm keyref="truck"/>
  </relatedTerms>
 </relations>
</termentry>
```
+++

> <i class="fa-solid fa-triangle-exclamation"></i> **CAUTION** **`<termentry>`** topics are not meant to be used or reused in a normal DITA project, they are just used for storing the terminology.

> <i class="fas fa-circle-info"></i> **INFO** If you have found a bug or want to request a feature, please raise a <i class="fa-brands fa-github"></i> [GitHub issue](https://github.com/stefan-jung/org.jung.terminology/issues).



Main Features
=============

* Create and change terms easily using specialized DITA topics. The new DITA `<termentry>` topic represents a single terminology concept. Terminology concepts are linked together to a terminology database using the new DITA `<termmap>` map.
* Author terminology concepts easily using an <oXygen/> XML framework, which is providing author mode stylesheets, which simplify the editing of `<termentry>` and `<termmap>` topics and maps.
* **Termbrowser** - Generate a responsive website for browsing through your terminology. Read more on [Terminology browser](/plugins/termbrowser.html)
* **Oxygen Terminology Checker** - Generate terminology checker rules for the [Oxygen Terminology Checker Add-on](https://www.oxygenxml.com/doc/versions/26.1/ug-editor/topics/terminology-checker-addon.html). Read more on [Oxygen Terminology Checker](/plugins/terminology-oxygen-terminology-checker.html). 
* **Termchecker for DITA and XLIFF** - Check terminology in DITA and XLIFF files with Schematron rules. Read more on [Termchecker for DITA and XLIFF](/plugins/terminology-checker-dita-xliff.html).
* **Terminology Harvester** - Harvest new terms from translation memories (.tmx) or XLIFF files (.xlf or .xliff). Read more on [Terminology Harvester](/plugins/terminology-harvester.html).
* **TBX/MARTIF** - You can generate TermBase eXchange (TBX) files to share your terminology with your translation vendor. Read more on [TermBase eXchange (TBX)/MARTIF](/plugins/terminology-tbx.html).

**Quick Start Presentation**: Recorded by [Syncro Soft/OxygenXML Editor](https://www.oxygenxml.com/about_us.html), DITA-OT Day 2016, Munich

<!-- Slides: [https://doctales.github.io/presentations/presentation-dita-ot-day/index.html](https://doctales.github.io/presentations/presentation-dita-ot-day/index.html) -->



Installation
============

Prerequisites
-------------

*   DITA-OT 3.x or DITA-OT 4.x
*   oXygen XML 23 or higher

  

Install the plugin to the DITA-OT
---------------------------------

You can install the plugin to the DITA-OT with a single command:

```xml
dita --install https://github.com/stefan-jung/org.jung.terminology/archive/master.zip
```

  

Installing the oXygen Framework
---------------------------

The oXygen framework helps you to author your terminology database. It consists of oXygen styles and actions that help you create and edit terms.

1.  In oXygen XML open the menu `Options` > `Preferences`.
2.  In the preferences, open `Document Type Association` > `Locations`.
3.  Add the directory of the plugin, e.g. `/home/user/workspace/DITA/dita-ot/plugins/org.jung.terminology`.

  

Using the plugin
================

**org.jung.terminology** ships a few sample files, that show you how to create terms and create the various outputs. To test the transformations, just open the `terminology.ditamap` in the oXygen DITA Maps Manager and run a transformation scenario.

This page explains how to use the termchecker for DITA. The DITA Termchecker is technically a [Schematron](http://www.schematron.com/) file, that searches for not recommended terms and replaces them with preferred synonyms. It is recommended [add a new document type association](http://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/preferences-document-type-association.html) by extending the `DITA` framework and [create a new validatation scenario](https://www.oxygenxml.com/doc/versions/18/ug-editor/tasks/create-validation-scenario.html) using the termchecker DITA Schematron file.


**Table of Contents**

*   [Parameters](#TermcheckerDITA-Parameters)
*   [Publishing a Termchecker for DITA using the dita command](#TermcheckerDITA-PublishingaTermcheckerforDITAusingtheditacommand)
*   [Publishing a Termchecker for DITA from oXygen XML](#TermcheckerDITA-PublishingaTermcheckerforDITAfromoXygenXML)

#### Parameters

The termchecker for DITA transformation supports the following parameters, that can be passed with `-Dparameter=value` to the dita command. You can find more information about parameters on [Building output using the dita command](http://www.dita-ot.org/dev/user-guide/build-using-dita-command.html).


##### Termchecker XLIFF Parameters

`args.language`
: Language of the terminology check rules. For example `de-DE`.


#### Publishing a Termchecker for DITA using the dita command

You can find more information about the dita command on [Building output using the dita command](http://www.dita-ot.org/dev/user-guide/build-using-dita-command.html).

  

**Example**

```xml
dita --input terminology.ditamap --format termchecker-dita -Dargs.language=en-GB --output termchecker-dita
```

#### Publishing a Termchecker for DITA from oXygen XML

1.  Open the samples DITA map `~/org.stefan.jung.terminology/samples/terminology.ditamap` in the oXygen DITA Maps Manager.
2.  In the `Transformation Scenarios` view, double click the entry `Termchecker for DITA`.  
    ![](attachments/40008098/40009202.png)  
      
    The terminology is transformed to the Schematron file `~/out/termchecker-dita/terminology-DITA-en-GB.sch`. By default, the terminology checker is generated for British English (`en-GB`). If you want to generate the terminology checker for another language, you have to change the parameter `args.language` of the transformation scenario.
3.  Create a new DITA validation scenario and refer to the generated Schematron file.
    1.  In oXygen open the menu `Options` > `Preferences`.
    2.  In the `Document Type Association` menu, select the `DITA` document type association and click the button`Edit`.
    3.  Open the `Validation` tab and click the + button, to create a new validation scenario.
    4.  Create a new validation scenario named `Terminology` and specify the Schematron schema.
        
4.  Create a new DITA topic.
5.  Set the `xml:lang` attribute of the topic to `en-GB` and write the word `truck` somewhere in the topic.  
    The term violation is indicated with a small lamp icon. Click on the lamp select the `Replace with an allowed term`action. This works both in text and in author mode.
      
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


#### Parameters

`args.check.elements`
: Choose whether terms should be checked only in source elements or target elements or in both of them. Possible values are `source`, `target`, `both`. Default value is `source`.

`args.language`
: This is the language of the terminology check rules, for instance `de-DE`.



The DITA Termbrowser Responsive (format: `termbrowser-reponsive`) is a reponsive website for browsing through your terminology database.

The _termbrowser responsive_ is based on the oXygen plugin **com.oxygenxml.webhelp.responsive** (**com.oxygenxml.webhelp** before <oXygen/> 19.1) and is used to browse through the terminology database.

#### Prerequisites

To publish the _termbrowser responsive_, you need to have the plugins **com.oxygenxml.webhelp.responsive** and **com.oxygenxml.webhelp.common** (since <oXygen/> 19.1) installed to your DITA-OT. This means, you need to use the DITA-OT which is shipped with Oxygen XML (because it contains all those plugins) or you need to use the [Oxygen Publishing Engine](https://www.oxygenxml.com/publishing_engine.html), if you want to use this on a server.

If you want to publish the _termbrowser responsive_ via command line interface, you need an additional license, see [Buy Oxygen XML WebHelp](https://www.oxygenxml.com/xml_webhelp/buy_oxygen_xml_webhelp.html).


#### Parameters

`args.default.language`
: Language used to generate the termbrowser labels, for instance `en-GB`.

`args.termstats`
: Relative path to the terminology statistics (`termstats.xml` file). The `termstats.xml` file is automatically generated with each termbrowser publication. If you pass the `termstats.xml` from the previous build with this parameter, you can generate a&nbsp;chronological sequence of your terminology metadata. Example: `../termstats.xml`


#### Example

```xml
dita --input terminology.ditamap --format termbrowser-responsive -Dargs.default.language=en-GB --output out/termbrowser-responsive
```

