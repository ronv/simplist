---
comments: true
date: "2019-08-31T00:00:00Z"
description: What is the difference between various font formats?
summary: What is the difference between various font formats?
categories:
- article
tags:
- typography
title: Difference between font formats
---

There are many different font formats, but most commonly are the following formats: OTF (OpenType), TTF (TrueType), SVG, EOT (Embedded Open Type), WOFF (Web Open Font Format), WOFF2. Fonts can be confusing since there are so many different font types. How can you decide which format you should use? Well, the first step is understanding the different types of fonts. Below I will explain all the different formats and what they are good for.

### TrueType Font (TTF)

TrueType is a digital font technology designed by Apple Computer, and now used by both Apple and Microsoft in their operating systems. Microsoft has distributed millions of quality TrueType fonts in hundreds of different styles, including them in its range of products and the popular TrueType Font Packs. TrueType fonts offer the highest possible quality on computer screens and printers, and include a range of features which make them easy to use. The TrueType font technology consists of two components: the TrueType fonts themselves, which come in many thousands of different styles, and can be purchased individually or in collections from font manufacturers; and the TrueType rasterizer, a piece of software built into System 7.x on the Apple Macintosh range of computers, and also into Microsoft's Windows family of operating systems. 

### OpenType (OTF)

OpenType is a font format developed jointly by Microsoft and Adobe as an extension of Apple’s TrueType font format. The OpenType 1.0 font specification was released in 1997. Since that time Adobe and Microsoft have continued to work together updating and refining the specification. Several other companies, including Apple and Monotype, have also contributed to the specification over the years. Currently, every major font foundry and most minor ones are developing fonts in OpenType format.

OpenType, like TrueType, is based on Unicode, the system for encoding all of the world’s writing systems. OpenType fonts can potentially contain many thousands of characters. This means that an OpenType font may contain multiple alphabets (such as Latin, Greek, and Cyrillic; or kanji, kana, and romaji for Japanese use). OpenType fonts can also include typographic refinements such as true small caps, different styles of figures, and extensive sets of ligatures and alternates, as well as complete sets of accented characters and diacritical marks. Different applications have differing levels of support for all the OpenType features. This font format is a superset of the existing TrueType and Type 1 formats, which is designed to provide great support for type in print and on-screen. In addition, the subsetting and compression technology of OpenType makes the OpenType initiative especially relevant to the Internet and the World Wide Web, since it allows for fast download of type.

OpenType handles all fonts with a unified registry, which means that both Type 1 and TrueType fonts will be reliably supported across all platforms. In addition, by working together Adobe and Microsoft will drive innovations in quality and on-screen support, resulting in better more viewable fonts for customers.

### Embedded OpenType (EOT)

Embedded OpenType font files are made small in size by use of subsetting (only including the needed characters), and by data compression (LZ compression, part of Agfa's MicroType Express). Like OTF fonts, EOT supports both Postscript and TrueType outlines for the glyphs.

Simply including fonts in webpages might lead to unrestricted copying of copyrighted font files. Embedded OpenType includes features to discourage copying. Subsetting reduces the value of copying, as subsetted fonts will typically omit more than half of the characters. Other copy protection measures used are encryption and a list of "trusted roots" at the source end, and a proprietary decrypting library at the receiving end.

If the embedded font is not available to the web page for any reason (missing font file, wrong keys in the file, non-support by the web browser), then the second-choice font specification is used, ensuring that the page should be readable even without the intended font.

Embedded OpenType is a proprietary standard supported exclusively by Internet Explorer but was submitted to the W3C in 2007 as part of CSS3, which was rejected and resubmitted as a standalone submission March 18, 2008. The W3C team comment on the submission states that the "W3C plans to submit a proposal to the W3C members for a working group whose goal is to try and develop EOT into a W3C Recommendation." However, the W3C ultimately chose a different web font format (WOFF) as a W3C Recommendation. The support for the format has not been built into the Microsoft Edge, the successor to the Internet Explorer.

### Web Open Font Format (WOFF)

The Web Open Font Format (WOFF) is a font format for use in web pages. WOFF files are OpenType or TrueType fonts, with format-specific compression applied and additional XML metadata added. The two primary goals are to first distinguish font files intended for use as web fonts from fonts files intended for use in desktop applications via local installation, and second to reduce web font latency when fonts are transferred from a server to a client over a network connection.

The WOFF format also allows additional metadata to be attached to the file; this can be used by font designers or vendors to include licensing or other information, beyond that present in the original font. Such metadata does not affect the rendering of the font in any way, but may be displayed to the user on request.

WOFF 2.0, with reference code provided by Google, has an improved compression scheme, using Brotli for byte-level compression, and became a W3C Recommendation in March 2018. The WOFF2 format offers a 30% average compression gain over the original WOFF.

### Scalable Vector Graphics font (SVG)

Scalable Vector Graphics (SVG) is an XML-based vector image format for two-dimensional graphics with support for interactivity and animation. The SVG specification is an open standard developed by the World Wide Web Consortium (W3C) since 1999.

SVG images and their behaviors are defined in XML text files. This means that they can be searched, indexed, scripted, and compressed. As XML files, SVG images can be created and edited with any text editor, as well as with drawing software.

All major modern web browsers—including Mozilla Firefox, Internet Explorer, Google Chrome, Opera, Safari, and Microsoft Edge—have SVG rendering support.

### So, what format should I use?

If you are a designer or a typesetter, you definitely want to pick OTF over TTF because of the extended features and added freedom it offers. If you need a web font for your website it is usually served in four formats, TrueType, WOFF, EOT and SVG. Only with four formats browser compatibility is achieved, as each browser uses a format.
