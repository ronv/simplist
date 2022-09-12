
---
date: "2021-08-07T00:00:00Z"
description: The new next-gen image compression format AVIF
summary: The new next-gen image compression format AVIF
categories:
- article
tags:
- avif
title: AVIF image format
---

AV1 Image File Format (AVIF) is a powerful new, open source, royalty-free file format that encodes AV1 bitstreams in the High Efficiency Image File Format (HEIF) container. The format was developed by the [Alliance for Open Media](http://aomedia.org/) in collaboration with Google, Cisco, and Xiph.org. AVIF generally has better compression than WebP, JPEG, PNG and GIF and is designed to supersede them. AVIF competes with JPEG XL which has similar compression quality and is generally seen as more feature-rich than AVIF.

## AVIF image format features

* Excellent lossy compression compared to JPG and PNG for visually similar compression levels.
* Better compression than WebP - median 50% vs 30% compression for the same JPG set (source: [AVIF WebP Comparision](https://www.ctrl.blog/entry/webp-avif-comparison.html)).
* Lossless compression.
* Animation/multi-image storage.
* Alpha channel support.
* High dynamic range (HDR).
* Any color space including wide color gamut, ISO/IEC CICP, and ICC profiles.
* 4:2:0, 4:2:2, 4:4:4 chroma subsampling.
* 8, 10, 12-bit color depth.
* Film grain.

## Why is AVIF better than its competitors?

More than a half of an average website's bandwidth is spent on images. Improved image compression can save bandwidth and improve overall performance of the web. The compression in AVIF is so good that images can reduce to half the size of JPEG and WebP. AVIF supports transparency, HDR, wide colour gamut and all of the things that the AV1 codec does. AVIF provides the highest compression possible, especially at low bit rates. AVIF was created in a royalty-free format which will make adoptions and usage much easier from a legal standpoint. It is currently backed by many big players in tech like Google, Amazon, Netflix, Microsoft, and more.

## Supported browsers

* Google Chrome,
* Mozilla Firefox,
* Opera.

If the AVIF image above doesn't show in your browser, try using the latest version of Google Chrome or by enabling AVIF in the Firefox advanced configuration preferences.

## How to implement AVIF in your website

The best way to implement it is using `<picture>` and `<source>` tags. This is so that if the browser doesn’t support the AVIF file type it will display the fallback image instead, which would be the JPEG.

```
<picture>
	<source srcset="img/example.avif" type="image/avif">
	<source srcset="img/example.webp" type="image/webp">
	<img src="img/example.jpg">
</picture>
```