---
title: Optimizing image loading for the web
date: 2020-12-29T08:59:48.092Z
description: How to optimize images for web and performance
tags:
  - html
---
According to [HTTP Archive](https://httparchive.org/reports/state-of-images) images make up for more than 60% of data loaded on website. Large images slow down your website which creates a less than optimal user experience. In this post, I’ll offer suggestions for optimizing images on your website.

### Lazy Load with `loading` attribute

Lazy-loading is a technique that defers loading of non-critical resources at page load time. Instead, these non-critical resources are loaded at the moment of need. Chrome and Firefox both support lazy-loading with the `loading` attribute. This attribute can be added to `<img>` elements, and also to `<iframe>` elements. A value of `lazy` tells the browser to load the image immediately if it is in the viewport, and to fetch other images when the user scrolls near them.

```html
<img src="cat.jpg" loading="lazy"/>
```

### Asynchronous decoding

The `<img>` tag can include a `decoding` attribute through which we can specify a hint to the browser whether decoding of the image should be done synchronously or asynchronously. `async` attribute will decode the image asynchronously. Rendering of page and decoding of image will be done in parallel. This obviously makes the page to render faster.

```html
<img src="cat.jpg" decoding="async"/>
```

### Cumulative Layout Shift (CLS)

Cumulative Layout Shift (CLS) is a Core Web Vitals metric, measures the instability of content by summing shift scores across layout shifts that don't occur within 500ms of user input. It looks at how much visible content shifted in the viewport as well as the distance the elements impacted were shifted.

One of the most common causes of a poor CLS are images without dimensions. Always include `width` and `height` size attributes on your images and video elements. Alternatively, reserve the required space with CSS aspect ratio boxes. This approach ensures that the browser can allocate the correct amount of space in the document while the image is loading.

```html
<style>
  img {
    max-width: 100%;
    height: auto;
  }
</style>
<!-- 16:9 aspect ratio -->
<img src="cat.jpg" width="640" height="360"/>
```

### Responsive images

With `srcset`, the browser does the work of figuring out which image is best. Defines multiple sizes of the same image, allowing the browser to select the appropriate image source.

```html
<!-- density descriptor -->
<img src="cat.jpg" 
     srcset="cat.jpg,
             cat_2x.jpg 2x"
/>

<!-- or width descriptor -->
<img src="cat.jpg" 
     srcset="cat-small.jpg 300w,
             cat-medium.jpg 600w,
             cat-large.jpg 900w"
/>
```

### WebP images

WebP is an image format developed and first released by Google in 2010. WebP images are smaller than their JPEG and PNG counterparts - usually on the magnitude of a 25–35% reduction in file size. This decreases page sizes and improves performance. People generally use one of the following approaches for converting their images to WebP: the [cwebp command-line tool](https://developers.google.com/speed/webp/docs/using) or the [Imagemin WebP plugin](https://github.com/imagemin/imagemin-webp) (npm package). The Imagemin WebP plugin is generally the best choice if your project uses build scripts or build tools (e.g. Webpack or Gulp), whereas the CLI is a good choice for simple projects or if you'll only need to convert images once.

```html
<img src="cat.webp" />
```

However since it's not always supported (see <http://caniuse.com/#feat=webp>), you can use this to set a fallback:

```html
<picture>
  <source srcset="cat.webp" type="image/webp">
  <source srcset="cat.jpg" type="image/jpeg"> 
  <img src="cat.jpg">
</picture>
```

### CDN for image delivery

A content delivery network (CDN) is a global network of servers that optimizes web performance by using the node closest to the user for faster delivery of assets. An Image CDN adds device detection and image optimization prior to delivering images from the CDN. An Image CDN decreases image payload, delivers images tailored exactly to each requesting device, ands instantly sends images from the edge of the network. The result is faster page loading that drives higher SEO ranking and better user experience.

Some of image optimization CDNs: [Imgix](https://www.imgix.com/), [Cloudinary](https://cloudinary.com/), [Akamai Image Manager](https://www.akamai.com/us/en/products/web-performance/image-manager.jsp), [ImageEngine](https://imageengine.io/). And APIs: [Kraken.io](https://kraken.io/), [Imagify](https://imagify.io/), [ShortPixel](https://shortpixel.com/), [Fastly Image Optimizer](https://docs.fastly.com/api/imageopto/), [TinyPNG](https://tinypng.com/).