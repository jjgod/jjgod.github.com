---
layout: default
title: A Comparison of Modern Text Layout Engines
---

I have been working on text layout [for][vim-cocoa] [a][itextus] [while][qt], things have changed a lot since I first started. Modern text layout engines like [Core Text][coretext], [DirectWrite][directwrite] and [HarfBuzz-ng][hb-ng] emerged and started to become the standard on each platforms. While legacy text engines like [ATSUI][atsui] and [Uniscribe][uniscribe] will co-exist for the time being, it's safe to say we are going to switch to at least one of these engines, either partially or fully. Given this fact, it will be interesting to compare these engines to see how different or how the same they are. This comparison is also part of my study to improve [Qt][qt] text layout backends.

[vim-cocoa]: http://code.jjgod.org/p/vim-cocoa
[itextus]: https://github.com/jjgod/iTextus
[qt]: http://qt.nokia.com
[coretext]: http://en.wikipedia.org/wiki/Core_Text
[directwrite]: http://msdn.microsoft.com/en-us/library/dd371554.aspx
[hb-ng]: http://www.freedesktop.org/wiki/Software/HarfBuzz
[atsui]: http://en.wikipedia.org/wiki/Apple_Type_Services_for_Unicode_Imaging
[uniscribe]: http://www.microsoft.com/typography/developers/uniscribe/

Fonts
-----

Font is the most important concept in text layout. The way we manipulate fonts is vital to a good text layout engine.

Although HarfBuzz is a full featured cross-platform layout engine, on Linux/Unix, the fonts manipulation part is largely dependent on [fontconfig][fontconfig] and [FreeType][freetype], thus, it makes more sense to compare Core Text and DirectWrite with them. Of course we will also include the interface to HarfBuzz.

[fontconfig]: http://fontconfig.org
[freetype]: http://freetype.org

### Font Matching

Font matching is process of find the font you want to use, in this phase you don't want to create the font yet, just want to see if the best match exist. A good font matching system should be able to find the closest match possible, yet the result should always conforms to other places (menu bar, text fields) in the same system.

#### Core Text

In Core Text, [`CTFontDescriptor`][ctfd] is responsible for font matching.

[ctfd]: http://developer.apple.com/library/mac/#documentation/Carbon/Reference/CTFontDescriptorRef/Reference/reference.html

### Font Fallback

### Font Enumeration

### Application Fonts Management

### Font Caching

