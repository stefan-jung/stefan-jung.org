---
title: Reveal plugin
permalink: /plugins/reveal.html
description: Plugin creating reveal.js based presentations
layout: page
eleventyNavigation:
  key: plugin-reveal
  parent: plugins
  title: Reveal.js plugin
  excerpt: DITA-OT plugin for generating HTML web slides using the HTML presentation framework reveal.js
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

[org.jung.reveal](https://github.com/stefan-jung/org.jung.reveal) is a DITA-OT plugin for generating HTML web slides based on the HTML presentation framework [reveal.js](http://lab.hakim.se/reveal-js/#/). This page should contain everything to get you started. To adapt the presentation to your needs, use the parameters explained below. If you have found a bug or want to request a feature, please raise an [issue](https://github.com/stefan-jung/org.jung.reveal/issues).


Installing the Plugin
=====================

Install the plugin using the `dita` command.
    
```bash
dita --install https://github.com/stefan-jung/org.jung.reveal/archive/master.zip
```
    
> **INFO**: The `reveal.js` framework ist not shipped by the plugin. It is automatically downloaded and extracted when publishing the first presentation.


Publishing the Sample Presentation
==================================

1.  Copy the `samples` directory from the plugin to your DITA workspace and rename it to `presentation`.
2.  Copy the `css` directory from the plugin to your new `presentation` directory.  
3.  Publish the presentation by calling the following command in the `presentation` directory.
    
    ```bash
    dita --input doctales.ditamap --format reveal -Dreveal.theme=doctales -Dreveal.css=css/doctales.css
    ```

Presentation Structure
======================

Creating a presentation is easy. A DITA topic represents a single slide and the DITA Map holds all topics/slides together. Take a look at the `Doctales.ditamap` in your `presentation` directory. 

**doctales.ditamap**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">
<map>
    <title>DOCTALES</title>
    <topicref href="topics/01_title.dita"/>
    <topicref href="topics/02_DOCTALES.dita"/>
</map>
```
  
The map contains references two to topics, each representing a top-level slide. The first topic contains the title and the logo.

**01\_title.dita**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "topic.dtd">
<topic id="title">
    <title>DOCTALES</title>
    <body>
        <fig>
            <image placement="break" href="https://doctales.github.io/images/doctales-logo.svg">
                <alt>DOCTALES Logo</alt>
            </image>
        </fig>
    </body>
</topic>
```

The second slide contains a title and nested topics, that are rendered as horizontal slides.

**02\_DOCTALES.dita**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "topic.dtd">
<topic id="doctales">
    <title>DOCTALES</title>
  
    <!-- First horizontal slide -->
    <topic id="who-are-we">
        <title>Who are we</title>
        <body>
            <p>We are a small team of technical writers with the vision of making
               DITA easier to use for small teams.</p>
            <ul>
                <li>Stefan Eike</li>
                <li>Sascha Nothofer</li>
            </ul>
        </body>
    </topic>

    <!-- Second horizontal slide -->
    <topic id="plugins">
        <title>What we are doing</title>
        <body>
            <ul>
                <li>We are developing <xref href="https://doctales.github.io/plugins/Plugins.html"
                    format="html" scope="external">plugins</xref> for the DITA-OT for various use cases.</li>
            </ul>
        </body>
    </topic>

    <!-- Third horizontal slide -->
    <topic id="support">
        <title>Support</title>
        <body>
            <ul>
                <li>If you want to join and support us, write an e-mail to <xref href="mailto:stefan.eike@mailbox.org" 
                    format="html" scope="external">stefan.eike@mailbox.org</xref>.</li>
                <li>If you need help with one of our plugins, write <xref href="http://stackoverflow.com/" 
                    format="html" scope="external">Stackoverflow topic</xref> and label it with 
                <i>DITA</i> and <i>DOCTALES</i>.</li>
                <li>If you have found a bug, please raise an issue on <xref href="http://github.com/doctales/"
                    format="html" scope="external">Github</xref>.</li>
            </ul>
        </body>
    </topic>

</topic>
```

Parameters
==========

| Parameter                              | Description                                                                                        |
|----------------------------------------|----------------------------------------------------------------------------------------------------|
| `reveal.autoslide`                | Number of milliseconds between automatically proceeding to the next slide, disabled when set to 0. |
| `reveal.autoslidestoppable`       | Stop auto-sliding after user input. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.backgroundtransition`     | Transition style for full page slide backgrounds. Possible values are `default`, `none`, `fade`, `slide`, `convex`, `concave`, `zoom`. Default value is `default`. |
| `reveal.center`                   | Vertical centering of slides. Possible values are `true` and `false`.Default value is `true`. |
| `reveal.controls`                 | Display controls in the bottom right corner. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.controlsLayout`           | Determines where controls appear. Possible values are `edges` and `bottom-right`. Default value is `edges`. |
| `reveal.css`                      | Path to CSS file, e.g. `~/org.stefan.jung/css/stefan-jung.css` |                                                                                                                  |
| `reveal.embedded`                 | Flags if the presentation is running in an embedded mode, i.e. contained within a limited portion of the screen. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.fragments`                | Turns fragments on and off globally. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.generate.vertical.slides` | Generate vertical slides for level 2 topics and below. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.height`                   | The 'normal' height of the presentation, aspect ratio will be preserved when the presentation is scaled to fit different resolutions. Can be specified using percentage units. Default value is `700`. |
| `reveal.hideaddressbar`           | Hides the address bar on mobile devices. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.history`                  | Push each slide change to the browser history. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.keyboard`                 | Enable keyboard shortcuts for navigation. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.loop`                     | Loop the presentation. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.margin`                   | Factor of the display size that should remain empty around the content. Default: `0.1` |
| `reveal.maxScale`                 | Bounds for largest possible scale to apply to content. Default: `1.5` |
| `reveal.minScale`                 | Bounds for smallest possible scale to apply to content. Default: `0.2` |
| `reveal.mousewheel`               | Enable slide navigation via mouse wheel. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.overview`                 | Enable the slide overview mode. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.parallaxbackgroundimage`  | Set the parallax background image. Example: `~/myimage.jpg` |
| `reveal.parallaxbackgroundsize`   | Parallax background size using CSS syntax. Example: `'2100px 900px'` |
| `reveal.previewlinks`             | Opens links in an iframe preview overlay. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.progress`                 | Display a presentation progress bar. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.rtl`                      | Change the presentation direction to be right-to-left. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.slidenumber`              | Display the page number of the current slide. Possible values are `true` and `false`. Default value is `false`. |
| `reveal.theme`                    | If you use a CSS template, the theme is namenameof the template is the filename without its extension. `sky`, `beige`, `simple`, `serif`, `night`, `moon`, `solarized` Default: `simple` |
| `reveal.touch`                    | Enables touch navigation on devices with touch input. Possible values are `true` and `false`. Default value is `true`. |
| `reveal.transition`               | Set the transition style. `default`, `none`, `fade`, `slide`, `convex`, `concave`, `zoom` Default: `default` |
| `reveal.transitionspeed`          | Set the transition speed. `default`, `fast`, `slow` Default: `default` |
| `reveal.version`                  | Set the reveal.js version. Default: latest |
| `reveal.viewdistance`             | Set the number of slides away from the current that are visible. Default: `3` |
| `reveal.width`                    | The 'normal' width of the presentation, aspect ratio will be preserved when the presentation is scaled to fit different resolutions. Can be specified using percentage units. Default: `960` |


Implement Font Awesome
======================

You can easily implement Font Awesome to use fancy icons in your presentation.

1.  Create a new XML file, e.g. hdf.xml.
2.  Add the following content:
    
    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <div>
        <link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet"><!-- --></link>
    </div>
    ```
    
3.  Set the property **args.hdf** and point it to your file.  
    `**${basedir}/resources/presentation/hdf.xml**`
4.  In your CSS theme, add:
    
    ```css
    /*********************************************
     * Font Awesome
     *********************************************/
    .reveal em.fa,
    .reveal em.fas {
      font-family: FontAwesome !important;
      font-style: normal;
    }
    ```

You can now add icons to your DITA content.

```xml
<p>This is awesome: <i outputclass="fas fa-exclamation"/></p>
```

Reveal.js Classes
=================

Reveal.js uses `@class` to enable certain functionality. Use `@outputclass` in your DITA source files to have them converted into `@class` in your web slides. For example, this example shows how [fragments](https://github.com/hakimel/reveal.js#fragments) can be used.

**@outputclass**

```xml
<section>
	<p outputclass="fragment grow">grow</p>
	<p outputclass="fragment shrink">shrink</p>
	<p outputclass="fragment fade-out">fade-out</p>
	<p outputclass="fragment fade-up">fade-up (also down, left and right!)</p>
	<p outputclass="fragment fade-in-then-out">fades in, then out when we move to the next step</p>
	<p outputclass="fragment fade-in-then-semi-out">fades in, then obfuscate when we move to the next step</p>
	<p outputclass="fragment highlight-current-blue">blue only once</p>
	<p outputclass="fragment highlight-red">highlight-red</p>
	<p outputclass="fragment highlight-green">highlight-green</p>
	<p outputclass="fragment highlight-blue">highlight-blue</p>
</section>
```

To add [speaker notes](https://github.com/hakimel/reveal.js#speaker-notes), you have two options in your DITA files. In any DITA topic type you can use `<div outputclass="notes">`. In the DOCTALES Slide topic type, you can also use the `<speakernotes>` element.
