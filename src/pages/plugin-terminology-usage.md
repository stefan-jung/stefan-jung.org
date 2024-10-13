---
title: Terminology plugin usage
permalink: /plugins/terminology-usage.html
description: Using the terimnology plugin
layout: page
eleventyNavigation:
  key: plugin-terminology-usage
  parent: plugin-terminology
  title: Terminology plugin usage
  excerpt: Using the terimnology plugin
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

**Quick Start Presentation**: Recorded by [Syncro Soft/OxygenXML Editor](https://www.oxygenxml.com/about_us.html), DITA-OT Day 2016, Munich

<!-- Slides: [https://doctales.github.io/presentations/presentation-dita-ot-day/index.html](https://doctales.github.io/presentations/presentation-dita-ot-day/index.html) -->

  

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

