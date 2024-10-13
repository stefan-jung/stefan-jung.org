---
title: Termbrowser
permalink: /plugins/termbrowser.html
description: Termbrowser of the terminology plugin
layout: page
eleventyNavigation:
  key: plugin-terminology-termbrowser
  parent: plugin-terminology
  title: Termbrowser
  excerpt: Termbrowser of the terminology plugin
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

The termbrowser is designed to browse through your terminology database. You can find an example generated from the provided sample files here: [stefanjung.netlify.app/termbrowser](https://stefanjung.netlify.app/termbrowser/). The termbrowser also contains a [semantic net](https://stefanjung.netlify.app/termbrowser/semantic-net/) and displays [statistics](https://stefanjung.netlify.app/termbrowser/semantic-net/termstats.html).

> <i class="fas fa-circle-info"></i> **INFO** To publish the _termbrowser responsive_, you need the _com.oxygenxml.responsive-webhelp_ plugin, which is part of the [Oxygen Publishing Engine](https://www.oxygenxml.com/publishing_engine.html), which is a customized version of the DITA-OT and is shipped with Oxygen XML. It does not work with a bare DITA-OT. If you would like to run this transformation on a publishing server, you need to buy a license for the [Oxygen XML WebHelp](https://www.oxygenxml.com/xml_webhelp/buy_oxygen_xml_webhelp.html).


Parameters
----------

##### General parameters

`debugging.mode`
: Activates the debugging mode.

`generate-termstats`
: Set this parameter to `true` to force the generation of a terminology statistics XML file. Usually the transtype tries to auto-detect if this should be done. The condition is fulfilled, if the transtype is 'termbrowser-responsive' and a &lt;termstatsref&gt; element needs to be available on the terminology map. But this does not work, if the transtype has been extended.` Possible values are `true` and `false`. Default value is `true`.

`args.termstats`
: Point this to a terminology statistics XML file from a previous build. If you save the terminology statistics every time you generate a term browser and feed them into the next build via this parameter, you can generate statistics over time.


#### Parameters for semantic net edges

`term.semantic-net.layout.improvedLayout`
: When enabled, the network will use the Kamada Kawai algorithm for initial layout. For networks larger than 100 nodes, clustering will be performed automatically to reduce the amount of nodes. This can greatly improve the stabilization times. If the network is very interconnected (no or few leaf nodes), this may not work and it will revert back to the old method. Possible values are `true` and `false`. Default value is `true`.

`term.semantic-net.edges.color.color`
: Color of semantic net edges as HTML color code. Color codes are must not be suffixed with a semicolon. Write '#96c3ff', not '#96c3ff;'.

`term.semantic-net.edges.color.highlight`
: Color of highlighted semantic net edges as HTML color code. Color codes are must not be suffixed with a semicolon. Write '#96c3ff', not '#96c3ff;'.

`term.semantic-net.edges.color.hover`
: Color of hovered semantic net edges as HTML color code. Color codes are must not be suffixed with a semicolon. Write '#96c3ff', not '#96c3ff;'.

`term.semantic-net.edges.width`
: Width of semantic net edges. Needs to be a numerical value, for example `5`. Default width is `1`.


#### Parameters for semantic net terms

`term.semantic-net.term.border`
: Semantic net term node border. Default value is `1`.

`term.semantic-net.term.background`
: Semantic net term node background

`term.semantic-net.term.font.color`
: Semantic net term node font color. Default color is `#1471bb`.

`term.semantic-net.term.font.size`
: Semantic net term node font size in px. Use only a digit. Default value is `9`.


#### Parameters for semantic net physics

`term.semantic-net.physics.stabilization.enabled`
: Toggle the stabilization. This is an optional property. If undefined, it is automatically set to true when any of the properties of this object are defined. Possible values are `true` and `false`. Default value is `true`.

`term.semantic-net.physics.stabilization.iterations`
: The physics module tries to stabilize the network on load up til a maximum number of iterations defined here. If the network stabilized with less, you are finished before the maximum number. Default value is `1000`.

`term.semantic-net.physics.stabilization.updateInterval`
: When stabilizing, the DOM can freeze. You can chop the stabilization up into pieces to show a loading bar for instance. The interval determines after how many iterations the stabilizationProgress event is triggered. Default value is `50`.

`term.semantic-net.physics.forceAtlas2Based.gravitationalConstant`
: This is similar to the barnesHut method except that the falloff is linear instead of quadratic. The connectivity is also taken into account as a factor of the mass. If you want the repulsion to be stronger, decrease the value (so -1000, -2000). Default value is `-50`.

`term.semantic-net.physics.forceAtlas2Based.centralGravity`
: There is a central gravity attractor to pull the entire network back to the center. This is not dependent on distance. Default value is `0.01`.

`term.semantic-net.physics.forceAtlas2Based.springLength`
: The edges are modelled as springs. This springLength here is the rest length of the spring. Default value is `100`.

`term.semantic-net.physics.forceAtlas2Based.springConstant`
: This is how 'sturdy' the springs are. Higher values mean stronger springs. Default value is `0.08`.

<!--
<video controls>
  <source src="../assets/images/termbrowser.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
-->
