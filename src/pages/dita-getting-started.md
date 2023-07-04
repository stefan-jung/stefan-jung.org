---
title: DITA Getting Started
description: 'Introduction to DITA and resources for learning it.'
layout: page
permalink: /dita-getting-started/index.html
---

This section helps you to get started with DITA if you are completely new to DITA. One of the disadvantages of DITA is, that the releveant information is quite fragmented and cluttered over various websites. Let this page be your compass guiding you through what's really relevant for you.


## Core concepts

Maybe you are at the very beginning right now and would like to ensure that DITA is really the right technology for you to learn. In this case, you maybe want to work through the quite comprehensive [dita-introduction](https://stefanjung.netlify.app/dita-introduction/), which I have created for you. It explains the basics of XML, DITA, the DITA history, and the unique functions which make DITA so powerful.

You can also find a recording of a presentation of this DITA introduction on Youtube:

**Write the Docs: Stefan Eike - DITA Introduction**
[![Write the Docs - Stefan Eike - DITA Introduction](http://img.youtube.com/vi/yxRv5n9w0I4/0.jpg)](http://www.youtube.com/watch?v=yxRv5n9w0I4 "Stefan Eike - DITA Introduction")


## Learning DITA

If you are now sure that DITA is the right technology for you to learn, you should work through [LearningDITA](http://learningdita.com/). This is a comprehensive, well-designed and free e-learning, which has been crafted by [Scriptorium](https://www.scriptorium.com).

This will give you a good base. You should also give read some parts of the [DITA 1.3 Specification](http://docs.oasis-open.org/dita/dita/v1.3/os/part3-all-inclusive/dita-v1.3-os-part3-all-inclusive.html). This may sound a bit strange, but the specification actually contains many useful examples that will help you.


## Specializing DITA

DITA ships a couple of specialized topic types, which are specialized from the core **[&lt;topic>](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/base/generictopics.html)** topic:

* [Concept topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-concept-topic.html)
* [Reference topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-reference-topic.html)
* [General task topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-generic-task-topic.html)
* [(Strict) task topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-task-topic.html)
* [Machinery task topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-machinerytask-topic.html#dita_spec_2_1_info_tasks)
* [Troubleshooting topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-troubleshooting-topic.html)
* [Glossary entry topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-glossary-topic.html)
* [Glossary group topic](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/technicalContent/dita-glossarygroup-topic.html)

*Specialization* helps you to add or remove XML elements and attributes or restrict their usage. By default, the DITA topics contains hundreds of elements, and probably you only need a subset. Let's assume that you don't need dedicated XML elements for explaining a software (because you create physical products). All DITA XML elements for explaining software are grouped in the *[Software](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/langRef/containers/sw-d.html)* domain. If you want to remove the entire domain and all its elements, you need to specialize new topic types (e.g. extending the concept and task topics). The concept of *specialization* is for sure the unique selling point of DITA. It allows you to create company-specific DITA grammars which are still fully compatible to the DITA specification.

> **Info**: Maybe you don't want to work with all these semantic XML elements. If you just need a very lightweight DITA environment, you might be interested in the [Lightweight DITA](http://docs.oasis-open.org/dita/LwDITA/v1.0/LwDITA-v1.0.html) project.

If you are sure you want to specialize DITA, you should read the chapter [Configuration, specialization, generalization, and constraints](http://docs.oasis-open.org/dita/dita/v1.3/errata02/os/complete/part3-all-inclusive/archSpec/base/configuration-specialization-and-constraints.html#configuration-specialization-and-constraints) of the specification. If you can understand German, the [data2type DITA specialization tutorials](https://www.data2type.de/xml-xslt-xslfo/dita/spezialisierung) will be useful for you. A little bit outdated, but still useful, are the ([Xiruss - DITA specialization tutorials](http://www.xiruss.org/tutorials/dita-specialization/) by W. Eliot Kimber.


* * *

*   [Blogs](#GettingStartedwithDITA-Blogs)
*   [DITA-Transformations](#GettingStartedwithDITA-DITA-Transformations)
*   [Style Guides](#GettingStartedwithDITA-StyleGuides)
*   [Youtube-Channels](#GettingStartedwithDITA-Youtube-Channels)
*   [Books](#GettingStartedwithDITA-Books)
*   [OASIS Feature Articles and Whitepapers](#GettingStartedwithDITA-OASISFeatureArticlesandWhitepapers)
*   [XSLT](#GettingStartedwithDITA-XSLT)
*   [Other](#GettingStartedwithDITA-Other)

* * *


DITA-Transformations
--------------------

*   [Scripto: DITA-to-PDF (Dita2pdf): there is more than the DITA Open Toolkit](http://de.slideshare.net/Scripto/ditatopdf-dita2pdf-there-is-more-than-the-dita-open-toolkit) - Alternative PDF publication method

Style Guides
------------

*   [The DITA Style Guide Best Practices for Authors](https://www.oxygenxml.com/dita/styleguide/webhelp-feedback/)[![](attachments/29229091/39754857.png)](https://github.com/hyperwrite/DITAStyleGuide) - The DITA Style Guide is designed to help DITA authors implement DITA consistently by providing an authoritative reference.
*   [Microsoft Manual of Style](https://www.microsoftpressstore.com/store/microsoft-manual-of-style-9780735648715) 


Books
-----

*   [DITA for Practitioners Volume 1: Architecture and Technology (Eliot Kimber)](https://read.amazon.com/kp/embed?asin=B00C7CC4HG&preview=newtab&linkCode=kpe&ref_=cm_sw_r_kb_dp_W-W7wb16PG4EG) - The most famous DITA book about the DITA basics.
*   [DITA for Print (Leigh W. White)](http://a.co/ghvODBp) \- A DITA-OT Workbook for customizing the output of the org.dita.pdf2 plugin.
*   [The Dita Style Guide: Best Practices for Authors (Tony Self)](http://www.amazon.com/dp/0982811810/ref=cm_sw_su_dp) - Contains best practices and real world DITA examples and comprehensive, practical explanations of DITA elements and attributes.

OASIS Feature Articles and Whitepapers
--------------------------------------

*   [DITA 1.3 Feature Article: About the DITA 1.3 release management domain](https://www.oasis-open.org/committees/download.php/56339/Release_Management_WP.pdf)
*   [DITA 1.3 Feature Article: Using DITA 1.3 Troubleshooting](https://www.oasis-open.org/committees/download.php/53516/DITA13TroubleshootingArticle_FINAL_03jul14.pdf)
*   [DITA 1.3 Feature Article: Understanding Scoped Keys in DITA 1.3](https://www.oasis-open.org/committees/download.php/56472/Understanding%20Scoped%20Keys%20In%20DITA%201.3.pdfhttps://www.oasis-open.org/committees/download.php/56472/Understanding%20Scoped%20Keys%20In%20DITA%201.3.pdf)
*   [DITA 1.2 Feature Article: Using XLIFF to Translate DITA Projects](http://www.ditatranslation.com/articles/ditaxliff.html)
*   [DITA 1.2 Feature Article: Roles and Responsibilities of a DITA Adoption](https://www.oasis-open.org/committees/download.php/50770/DITA_Roles_Responsibilities_final.pdf)
*   [DITA 1.2 Feature Article: Acronym Best Practices](https://www.oasis-open.org/committees/download.php/38692/DITA1.2FeatureDescriptionAcronym.pdf)
*   [DITA 1.2 Feature Overview: Domain and topic integration](https://www.oasis-open.org/committees/download.php/35163/domain_and_topic_integration_v0_2.pdf)
*   [DITA Feature Article: Short Descriptions Shouldn't Be a Tall Order: WritingEffective Short Descriptions](https://www.oasis-open.org/committees/download.php/57803/DITA-Adoption_2016_Writing-Effective-Short-Descriptions.pdf)
*   [DITA 1.2 Feature Description: Improved glossary and terminology handling](https://www.oasis-open.org/committees/download.php/35766/glossary_and_term_management.pdf)

XSLT
----

*   [data2type XSLT tutorials](https://www.data2type.de/en/xml-xslt-xslfo/xslt/)
*   [w3schools XSLT tutorials](https://www.w3schools.com/xml/xsl_intro.asp)


DITA Communities
----------------

*   [DITA Awareness Group (Linkedin)](https://www.linkedin.com/groups/162465) - DITA community on Linkedin.
*   [DITA Group (Xing)](https://www.xing.com/communities/groups/darwin-information-typing-architecture-dita-ba2f-1012092) - DITA community on Xing.
*   [DITA For Publishers](http://www.dita4publishers.org/) - The general goal of the DITA for Publishers project is to make creating and using DITA-based solutions for Publishing-specific business challenges as quick and easy as possible by providing a solid base from which you can start immediately.
*   [DITA-Community](http://www.dita-community.org/) - The DITA-Community is a place for DITA-OT plugins and sample files.
*   [DITANAUTS](http://ditanauts.org/) - The goal of the DITANAUTS project is to provide relevant, actionable information that helps others with the implementation of DITA.
*   [DITA Chicks](https://ditachicks.wordpress.com/) - DITA Chicks is a blog of Karen Lowe and Lu Hall covering various DITA related topics.
    
*   [oXygen XML DITA Forum](https://www.oxygenxml.com/forum/forum20.html) - The DITA forum of the oXygen XML editor is an important information resource and has great supporters and moderators.


Mailing Lists
-------------

*   [dita-users (Yahoo)](https://groups.yahoo.com/group/dita-users) - Biggest DITA mailing list
*   [oxygen-users](https://www.oxygenxml.com/mailinglists.html#oxygen-user) - Mailing list of the oXygen XML editor
*   [dita-ot-users (Google)](https://groups.google.com/forum/#!forum/dita-ot-users) - Another DITA mailing list, focussed on the DITA-OT.


Here we present tools, that can be used to create, edit and process DITA files.

#### Editors

*   [oXygen XML](http://oxygenxml.com) (Commercial) - The leading DITA XML editor.
*   [FrameMaker](http://www.adobe.com/de/products/framemaker.html) (Commercial) - DITA XML editor with powerful desktop publishing features.
*   [Xopus](http://www.sdl.com/solution/knowledge-delivery/xml-publishing-xopus/) (Commercial) - Web-based DITA XML editor
*   [Xeditor](http://www.xeditor.com/portal) (Commercial) - Web-based DITA XML editor
*   [XMetaL Author](http://xmetal.com/content-xmetal-author/) (Commercial) - XML editor
*   [XMLMind](http://www.xmlmind.com/xmleditor/download.shtml) (free for personal use) - Commercial XML editor, uses own DITA processing engine (not DITA-OT)
*   [Arbortext Editor](http://www.ptc.com/service-lifecycle-management/arbortext/editor) (Commercial) - XML editor
*   [Atom](https://atom.io/) (Open Source - [MIT](https://opensource.org/licenses/MIT)) - Modern, customizable text editor, can be customized to work as a basic XML editor
*   [FontoXML](https://dita.fontoxml.com/editor) (Commercial) - Modern, web-based XML editor.
    
    [You can use FontoXML for free](http://dita.fontoxml.com/), when using it with Google Drive or Microsoft OneDrive. It is also possible to setup a Git repository and keep that in your Google Drive or Microsoft OneDrive to collaborate with others.
    
*   [Codex](http://www.codex.ca/index.html) (Free for commercial and non-commercial use) - Simple DITA editor
*   Eclipse (Open Source - EPL) - Can be enhanced to be used as a DITA editor, see [Adding DITA to Eclipse](http://blog.artifact-software.com/tech/?p=220) by Ron Wheeler
*   [jEdit](http://www.jedit.org/) (Open Source - GPL2) - Customizable text editor. Install the XML plugin and then add the catalog-dita.xml in the plugin settings to make DITA validation work.

  

#### Content Management Systems

*   [Astoria CMS](http://www.astoriasoftware.com/) (Commercial)
*   [CloudDrafts](http://www.webworks.com/Products/CloudDrafts/) (Commercial)
*   [Componize DITA CMS](http://www.componize.com/) (Commercial)
*   [DITA Exchange DX4](http://www.ditaexchange.com/) (Commercial)
*   [DITAToo CMS](http://www.intuillion.com/) (Commercial)
*   [DITAworks](http://ditaworks.com/) (Commercial)
*   [DocZone DITA CCMS](http://www.rsicms.com/doczone) (Commercial)
*   [easyDITA](http://easydita.com/) (Commercial)
*   [Empolis Smart Content Express](http://empolis.com/microsites/content-express/en/) (Commercial)
*   [IXIASOFT DITA CMS](http://www.ixiasoft.com/en/products/) (Commercial)
*   [RSI Content Solutions RSuite](http://www.rsicms.com/rsuite-enterprise-publishing-solution) (Commercial)
*   [SDL Knowledge Center](http://www.sdl.com/cxc/knowledge-delivery/documentation-management-dita/) (Commercial)
*   [Vasont DITA CMS](https://www.vasont.com/) (Commercial)
*   [XDocs CCMS](http://www.bluestream.com) (Commercial)
*   [XML Documentation Add-on for Adobe Experience Manager](http://www.adobe.com/products/xml-documentation-add-on-for-experience-manager.html) (Commercial)
*   [XPLM Publisher](http://www.xplm.com/publisher) (Commercial)

  

#### Controlled Version Systems

*   [oxygen-git-plugin](https://github.com/oxygenxml/Oxygen-Git-Plugin) (Open Source - [APL2](https://www.apache.org/licenses/LICENSE-2.0)) - oXygen XML plugin that provides a simple Git client

  

#### Conversion

*   [Migrate](http://www.stilo.com/products/conversion/) (Commercial) - Cloud service with automatic conversion of various formats, e.g. FrameMaker or Word to DITA.
*   [oxygen-resources-convertor](https://github.com/oxygenxml/oxygen-resources-convertor) (Open Source - [APL2](https://www.apache.org/licenses/LICENSE-2.0)) - oXygen XML plugin to convert resources from various formats (e.g. HTML, Markdown) to DITA  
    

  

#### Comparison

*   [DeltaXML](https://www.deltaxml.com/) (Commercial) - Tool to compare and merge DITA

  

#### Translation

*   [Fluenta DITA Translation Manager](http://www.maxprograms.com/products/fluenta.html) (Commercial) - Tool to convert DITA to XLIFF for sending it to a translator. Contains a small translation management system.
*   [Translation-Package-Builder](https://github.com/oxygenxml/Translation-Package-Builder) (Open Source - [APL2](https://www.apache.org/licenses/LICENSE-2.0)) - oXygen XML plugin to generate translation packages from DITA

  

#### Online Platforms and Publishing Solutions

*   [4Dpubs](https://github.com/turbonomic/4Dpubs) (Open Source - [MIT](https://opensource.org/licenses/MIT)) - Renders DITA directly in the browser with XSLT.
*   [DITAweb](http://congility.com/ditaweb) (Commercial)
*   [ePublisher](http://www.webworks.com/Products/ePublisher/) (Commercial)
*   [Fluid Topics](http://www.fluidtopics.com) (Commercial) - Online Platform for hosting DITA content.
*   [oXygen XML WebHelp](https://www.oxygenxml.com/xml_webhelp.html) (Commercial)
*   [SuiteHelp](http://suite-sol.com/products/suitehelp/) (Commercial)
*   [Zoomin Docs](http://www.zoominsoftware.com/) (Commercial) - Portal for documentation and knowledge bases.

  

#### Print Solutions

*   [DITA InPrint™](http://www.ditainprint.com) (Commercial)
*   [IdXML – DITA to Adobe InDesign](http://congility.com/idxml/) (Commercial)
*   [MiramoPDF](http://www.miramo.com/download/documentation/Miramo_DITA-OT_Readme.pdf) (Commercial)
*   [TopLeaf XML Publisher](http://www.topleaf.com.au) (Commercial)

  

#### Metadata/Search

*   [oxygen-dita-prolog-updater](https://github.com/oxygenxml/oxygen-dita-prolog-updater) (Open Source - [APL2](https://www.apache.org/licenses/LICENSE-2.0)) - oXygen XML plugin to update metadata information in topics and maps
*   [ditasearch](https://github.com/shaneataylor/ditasearch) - DITA-OT plugin to build a search index and search box for HTML5 output

  

#### Analytics/Metrics

*   [dita-metrics-report](https://github.com/oxygenxml/dita-metrics-report) (Open Source - [MPL2](https://www.mozilla.org/en-US/MPL/2.0/)) - DITA-OT plugin that creates metrics reports from DITA projects