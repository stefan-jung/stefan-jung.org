---
title: Reveal plugin
permalink: /plugins/reveal.html
description: Plugin creating reveal.js based presentations
layout: page
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[org.doctales.reveal](https://github.com/doctales/org.doctales.reveal) is a DITA-OT plugin for generating HTML web slides based on the HTML presentation framework [reveal.js](http://lab.hakim.se/reveal-js/#/). This page should contain everything to get you started. To adapt the presentation to your needs, use the parameters explained below. If you have a question, go to the [questions](https://doctales.atlassian.net/wiki/display/reveal/questions/onboarding) section and ask the DOCTALES team. If you have found a bug or want to request a feature, please raise an [issue](https://github.com/doctales/org.doctales.reveal/issues).


Installing the Plugin
=====================

1.  Move to the `~/bin` directory of the DITA-OT.
2.  Install the plugin using the dita command.
    
    ```xml
    dita --install https://github.com/doctales/org.doctales.reveal/archive/master.zip
    ```
    
    > **INFO**: The `reveal.js` framework ist not shipped by the plugin. It is automatically downloaded and extracted when publishing the first presentation.
    

  

Publishing the Sample Presentation
==================================

1.  Copy the `samples` directory from the plugin to your DITA workspace and rename it to `presentation`.
2.  Copy the `css` directory from the plugin to your new `presentation` directory.  
3.  Publish the presentation by calling the following command in the `presentation` directory.
    
    ```bash
    dita --input doctales.ditamap --format reveal -Dargs.reveal.theme=doctales -Dargs.reveal.css=css/doctales.css
    ```

Presentation Structure
======================

Creating a presentation is easy. A DITA topic represents a single slide and the DITA Map holds all topics/slides together. Take a look at the `doctales.ditamap` in your `presentation` directory. 

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

<table class="wrapped confluenceTable"><colgroup><col><col><col></colgroup><tbody><tr><th class="confluenceTh">Parameter</th><th colspan="1" class="confluenceTh">Values</th><th class="confluenceTh">Description</th></tr><tr><td colspan="1" class="confluenceTd"><div class="content-wrapper"><p class="auto-cursor-target"><code>args.reveal.autoslide</code></p></div></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd"><span>Number of milliseconds between automatically proceeding to the next slide, disabled when set to <code>0</code>.</span></td></tr><tr><td colspan="1" class="confluenceTd"><p class="auto-cursor-target"><code>args.reveal.autoslidestoppable</code></p></td><td colspan="1" class="confluenceTd"><div class="content-wrapper"><p class="auto-cursor-target">"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></div></td><td colspan="1" class="confluenceTd"><span>Stop auto-sliding after user input.</span></td></tr><tr><td colspan="1" class="confluenceTd"><p class="auto-cursor-target"><code>args.reveal.backgroundtransition</code></p></td><td colspan="1" class="confluenceTd"><div class="content-wrapper"><p>"<code>default</code>", "<code>none</code>", "<code>fade</code>", "<code>slide</code>", "<code>convex</code>", "<code>concave</code>", "<code>zoom</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>default</code></p></div></td><td colspan="1" class="confluenceTd"><span>Transition style for full page slide backgrounds.</span></td></tr><tr><td colspan="1" class="confluenceTd"><p class="auto-cursor-target"><code>args.reveal.center</code></p></td><td colspan="1" class="confluenceTd"><div class="content-wrapper"><p class="auto-cursor-target">"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></div></td><td colspan="1" class="confluenceTd"><span>Vertical centering of slides.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.controls</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Display controls in the bottom right corner.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.controlsLayout</code></td><td colspan="1" class="confluenceTd"><p><span class="pl-c">"<code>edges</code>", "<code>bottom-right</code>"</span></p><p><span class="pl-c"><strong>Default</strong>: <code>edges</code></span></p></td><td colspan="1" class="confluenceTd"><p><span class="pl-c">Determines where controls appear</span></p></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.css</code></td><td colspan="1" class="confluenceTd"><br></td><td colspan="1" class="confluenceTd">Path to CSS file, e.g. <code>~/org.doctales.reveal/css/doctales.css</code></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.embedded</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Flags if the presentation is running in an embedded mode, i.e. contained within a limited portion of the screen.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.fragments</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Turns fragments on and off globally.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.generate.vertical.slides</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Generate vertical slides for level 2 topics and below.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.height</code></td><td colspan="1" class="confluenceTd"><strong>Default</strong>: <code>700</code></td><td colspan="1" class="confluenceTd"><span>The 'normal' height of the presentation, aspect ratio will be preserved when the presentation is scaled to fit different resolutions. Can be specified using percentage units.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.hideaddressbar</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Hides the address bar on mobile devices.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.history</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Push each slide change to the browser history.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.keyboard</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Enable keyboard shortcuts for navigation.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.loop</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Loop the presentation.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.margin</code></td><td colspan="1" class="confluenceTd"><strong>Default</strong>: <code>0.1</code></td><td colspan="1" class="confluenceTd"><span>Factor of the display size that should remain empty around the content.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.maxScale</code></td><td colspan="1" class="confluenceTd"><strong>Default</strong>: <code>1.5</code></td><td colspan="1" class="confluenceTd"><span>Bounds for largest possible scale to apply to content.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.minScale</code></td><td colspan="1" class="confluenceTd"><strong>Default</strong>: <code>0.2</code></td><td colspan="1" class="confluenceTd"><span>Bounds for smallest possible scale to apply to content.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.mousewheel</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Enable slide navigation via mouse wheel.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.overview</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Enable the slide overview mode.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.parallaxbackgroundimage</code></td><td colspan="1" class="confluenceTd"><strong>Example</strong>: <code>~/myimage.jpg</code></td><td colspan="1" class="confluenceTd"><span>Set the parallax background image.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.parallaxbackgroundsize</code></td><td colspan="1" class="confluenceTd"><strong>Example</strong>: <code><span>'2100px 900px'</span></code></td><td colspan="1" class="confluenceTd"><span>Parallax background size using CSS syntax.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.previewlinks</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Opens links in an iframe preview overlay.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.progress</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Display a presentation progress bar.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.rtl</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Change the presentation direction to be right-to-left.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.slidenumber</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>false</code></p></td><td colspan="1" class="confluenceTd"><span>Display the page number of the current slide.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.theme</code></td><td colspan="1" class="confluenceTd"><p>"<code>doctales</code>", "<code>default</code>", "<code>sky</code>", "<code>beige</code>", "<code>simple</code>", "<code>serif</code>", "<code>night</code>", "<code>moon</code>", "<code>solarized</code>"</p><p class="auto-cursor-target"><strong>Default:</strong> <code>simple</code></p></td><td colspan="1" class="confluenceTd">If you use a CSS template, the theme is namename<br>of the template is the filename without its<br>extensions, e.g. <code>doctales</code>.</td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.touch</code></td><td colspan="1" class="confluenceTd"><p>"<code>true</code>", "<code>false</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>true</code></p></td><td colspan="1" class="confluenceTd"><span>Enables touch navigation on devices with touch input.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.transition</code></td><td colspan="1" class="confluenceTd"><p>"<code>default</code>", "<code>none</code>", "<code>fade</code>", "<code>slide</code>", "<code>convex</code>", "<code>concave</code>", "<code>zoom</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>default</code></p></td><td colspan="1" class="confluenceTd"><span>Set the transition style.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.transitionspeed</code></td><td colspan="1" class="confluenceTd"><p>"<code>default</code>", "<code>fast</code>", "<code>slow</code>"</p><p class="auto-cursor-target"><strong>Default</strong>: <code>default</code></p></td><td colspan="1" class="confluenceTd"><span>Set the transition speed.</span></td></tr><tr><td colspan="1" class="confluenceTd"><pre>args.reveal.version</pre></td><td colspan="1" class="confluenceTd"><strong>Default</strong>: 3.8.0</td><td colspan="1" class="confluenceTd">Set the reveal.js version.</td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.viewdistance</code></td><td colspan="1" class="confluenceTd"><p class="auto-cursor-target"><strong>Default</strong>: <code>3</code></p></td><td colspan="1" class="confluenceTd"><span>Set the number of slides away from the current that are visible.</span></td></tr><tr><td colspan="1" class="confluenceTd"><code>args.reveal.width</code></td><td colspan="1" class="confluenceTd"><strong>Default</strong>: <code>960</code></td><td colspan="1" class="confluenceTd"><span>The 'normal' width of the presentation, aspect ratio will be preserved when the presentation is scaled to fit different resolutions. Can be specified using percentage units.</span></td></tr></tbody></table>

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

