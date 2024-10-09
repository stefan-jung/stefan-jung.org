---
title: TermBase eXchange (TBX)/MARTIF
permalink: /plugins/terminology-tbx.html
description: Share your terminology with your translation vendor as TBX files
layout: page
eleventyNavigation:
  key: plugin-terminology-tbx
  parent: plugin-terminology
  title: TermBase eXchange (TBX)/MARTIF
  excerpt: Share your terminology with your translation vendor as TBX files
preloads:
  href: '/assets/fonts/robotomono/robotomono-variablefont_wght-webfont.woff2'
  as: 'font'
  type: 'font/woff2'
  crossorigin: true
---

[Parent: Terminology plugin](/plugins/terminology.html)

TBX is a data format to exchange a terminology database, e.g. to pass it to your Language Service Provider (LSP). This ensures that the translator uses the correct terminology during translation.

The terminology plugin provides several dialects. You'll surely find one which is suitable for your needs.

The following transformation scearios are available:

TBX Basic
--------

[TBX-Basic](http://www.ttt.org/oscarstandards/tbx/tbx-basic.html) is a lighter version of the Terminology Base Exchange (TBX) format. You can choose between the transformations `tbx-basic-v2` and `tbx-basic-v3`.


#### Parameters

The transformation `tbx-basic-v3` allows the following parameters.

`debugging.mode`
: Activates the debugging mode. Possible values are `true` and `false`. Default value is `false`.
 
`main.language`
: Default language for definitions and so forth, for instance `en-US`.


TBX Min
-------

[TBX-Min](https://www.tbxinfo.net/tbx-modules/?id=4) is a dialect of the TermBase eXchange (TBX) format and is designed for bilingual or monolingual glossaries. The TBX-Min format is explained in the paper [TBX - Min: A Simplified TBX - Based Approach to Representing Bilingual Glossaries](http://www.tbxinfo.net/wp-content/uploads/2016/10/lommel_melby_glenn_hayes_snow-final.pdf). You can choose between the transformations `tbx-min-v3-dca` and `tbx-min-v3-dct`.

#### Parameters

`source.language`
: Source language of terminology. **Example**: `de-DE` (German/Germany)

`target.language`
: Target language of terminology. **Example**: `en-GB` (English/Great Britain)

`license`
: License information to be added in the header.

Multiterm
---------

The following transformation scenarios generate RWS Multiterm XML files. You can choose between the transformations `multiterm` and `multiterm-custom`. The transformation `multiterm-custom` is tailored for special requirements when your translation vendor is RWS.

#### Parameters

`debugging.mode`
: Activate the debugging mode. Possible values are `true` and `false`. Default value is `false`.