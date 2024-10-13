---
title: Terminology Checker for DITA and XLIFF
permalink: /plugins/terminology-checker-dita-xliff.html
description: Schematron rules for checking terminology in DITA and XLIFF files
layout: page
eleventyNavigation:
  key: plugin-terminology-checker-dita-xliff
  parent: plugin-terminology
  title: Terminology Checker for DITA and XLIFF
  excerpt: Schematron rules for checking terminology in DITA and XLIFF files
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

You can search for not recommended terms in DITA and XLIFF files with Schematron rules. You can generate them with the  with the `termchecker-dita` and `termchecker-xliff` transformations. These Schematron rules suggest corresponding preferred synonyms.

> **NOTE** You can create an Oxygen validation scenario to perform these checks automatically.
> 

Termchecker DITA
---------------

The transformation `termchecker-dita` generates Schematron rules for DITA topics.


#### Parameters

`debugging.mode`
: Activates the debugging mode. Possible values are `true` and `false`. Default value is `false`.

`args.language`
: Language of the terminology check rules, for instance `en-US`.


Termchecker XLIFF
----------------


#### Parameters

`debugging.mode`
: Activates the debugging mode. Possible values are `true` and `false`. Default value is `false`.

`args.check.elements`
: Choose whether terms should be checked only in source elements or target elements or in both of them.

`args.language`
: Language of the terminology check rules.

















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

**Quick Start Presentation**: Recorded by [Syncro Soft/OxygenXML Editor](https://www.oxygenxml.com/about_us.html), DITA-OT Day 2016, Munich

<!-- Slides: [https://doctales.github.io/presentations/presentation-dita-ot-day/index.html](https://doctales.github.io/presentations/presentation-dita-ot-day/index.html) -->

  

Using the plugin
================

**org.jung.terminology** ships a few sample files, that show you how to create terms and create the various outputs. To test the transformations, just open the `terminology.ditamap` in the oXygen DITA Maps Manager and run a transformation scenario.

This page explains how to use the termchecker for DITA. The DITA Termchecker is technically a [Schematron](http://www.schematron.com/) file, that searches for not recommended terms and replaces them with preferred synonyms. It is recommended [add a new document type association](http://www.oxygenxml.com/doc/versions/19.0/ug-editor/topics/preferences-document-type-association.html) by extending the `DITA` framework and [create a new validatation scenario](https://www.oxygenxml.com/doc/versions/18/ug-editor/tasks/create-validation-scenario.html) using the termchecker DITA Schematron file.

> <i class="fas fa-circle-info"></i> **INFO** To learn how to validate your DITA topics with the Schematron termchecker, read [Creating a New Validation Scenario](https://www.oxygenxml.com/doc/versions/26.1/ug-editor/topics/create-validation-scenario.html).


