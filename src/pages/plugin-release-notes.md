---
title: Plugins
permalink: /plugins/release-notes.html
description: Plugin for generating release notes of DITA docs
layout: page
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[org.doctales.release-notes](https://github.com/doctales/org.doctales.release-notes) is a plugin for the [DITA-OT](http://dita-ot.github.io/) that extends the **org.dita.pdf2** plugin to automatically create release-notes lists or tables from the [DITA 1.3 release-management domain elements](http://docs.oasis-open.org/dita/dita/v1.3/os/part3-all-inclusive/archSpec/technicalContent/releaseManagement-domain.html#dita_release_management_domain_topic). If you have a question, go to the [questions](https://doctales.atlassian.net/wiki/display/J2D/questions/onboarding) section and ask the DOCTALES team. If you have found a bug or want to request a feature, please raise an [issue](https://github.com/doctales/org.doctales.javaProperties2Dita/issues).

To learn more about the **release-management domain**, read the official [DITA 1.3 release management domain feature article](https://www.oasis-open.org/committees/download.php/56339/Release_Management_WP.pdf).

  

Installation
============

You can directly install the plugin to the DITA-OT by calling the `dita` command with the `--install` parameter and point it to the `master.zip` that contains the latest changes checked in on the `master` branch on the [GitHub repository](https://github.com/doctales/org.doctales.release-notes).

dita --install https://github.com/doctales/org.doctales.release-notes/archive/master.zip

  
Using the Plugin
================

Add a `<booklist type="change-historylist"/>` element as a child of a `<booklists>` element on your `<bookmap>`, for example:

```xml
<frontmatter>
    <booklists>
        <toc/>
        <booklist type="change-historylist"/>
    </booklists>
</frontmatter>
```

Add `<change-list>` elements to your DITA Maps and DITA Topics to reflect your changes. It is mandatory, that you use the `<change-completed>` elements to clarify, when a change has been made. This date is needed to calculate, whether the change has been made _before_ or _after_ a specific book release date.

```xml
<change-historylist>
    <change-item>
        <change-person>John Smythe</change-person>
        <change-organization>Engineering</change-organization>
        <change-revisionid>topic-change-001</change-revisionid>
        <change-request-reference>
            <change-request-system>BugTracker Pro</change-request-system>
            <change-request-id>BT001</change-request-id>
        </change-request-reference>
        <change-started>2014-10-15</change-started>
        <change-completed>2014-10-22</change-completed>
        <change-summary>Description of new foo feature added.</change-summary>
        <data>New feature addition for v3, originally relating from a UI change request that came in from a customer</data>
    </change-item>
</change-historylist>
```

You need to specify the creation and revision dates of the book in a `<critdates>` element on your `<bookmap>`.

```xml
<critdates>
    <created date="2015-01-01"/>
    <revised modified="2015-02-01"/>
    <revised modified="2015-03-01"/>
    <revised modified="2016-04-01"/>
</critdates>
```

Publish a `pdf2` based PDF. You can optionally set the `changelist.style` property to `table` to publish the changes in a table format, for example:

dita --input your.ditamap --format pdf -Dchangelist.style=table

Using the Plugin with custom pdf2 based Plugins
===============================================

If you like to use this plugin with custom `pdf2` based plugins that use a shell XSL file which is passed to the DITA-OT by using the `args.xsl.pdf` extension point, you need to add some additional `<xsl:import>` statements to make this plugin work correctly.

This is, for example, the case, when you have generated your plugin using the [dita-generator](http://dita-generator-hrd.appspot.com/).

At the top of your shell XSL add:

  

```xml
<xsl:import href="plugin:org.dita.pdf2:xsl/fo/topic2fo.xsl"/>
```

At the bottom of your shell XSL add:

  

```xml
<xsl:import href="plugin:org.doctales.release-notes:xsl/fo/root-processing.xsl"/>
<xsl:import href="plugin:org.doctales.release-notes:cfg/fo/attrs/release-notes.xsl"/>
<xsl:import href="plugin:org.doctales.release-notes:xsl/fo/release-notes.xsl"/>
```

  
Because you now have added a hard dependency to **org.doctales.release-notes**, you should explicitely name it so by adding the following `<require>` element to your **plugin.xml**:

  

```xml
<require plugin="org.doctales.release-notes"/>
```

Sample Files
============

You can test the plugin with this simple project. Please investigate the elements **`<change-historylist>`**, `**<critdates>**` and **`<booklist>`** in the bookmap and the topic.

1.  Extract the ZIP archive.
2.  Publish using the dita command.
    
    ```bash
    dita --input release-notes.ditamap -Dchangelist.style=list --format pdf2
    ```