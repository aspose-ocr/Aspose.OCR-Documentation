---
weight: 20
date: "2023-12-11"
author: "Vladimir Lapin"
type: docs
url: /nodejs-cpp/supported-file-formats/
title: Supported file formats
description: File formats for images and recognition results supported by Aspose.OCR for Node.js via C++.
keywords:
- format
- image
- data
- source
- result
- scan
- photo
---

## Recognized image formats

Aspose.OCR for Node.js via C++ is capable of recognizing text from any file obtained through a scanner or camera:

File format             | Details
--------------------- | -------
**JPEG** (_.JPG_ or _.JPEG_) | The most popular format for smartphone photos.
**PNG** (_.PNG_)             | 24-bit Portable Network Graphics with transparency.
**TIFF** (_.TIF_ or _.TIFF_) | Tag Image File Format, commonly used for high quality scanning. Multi-page TIFF images are fully supported.
**Bitmap** (_.BMP_)          | Bitmap image file.
**Archive** (_.ZIP_)         | All JPEG, PNG, TIFF and BMP images inside the archive.<sup>(1)</sup>
**Web link**                 | A public URL to JPEG, PNG, TIFF and BMP image.<sup>(2)</sup>

{{% alert color="caution" %}}
1. Aspose.OCR for Node.js via C++ engine can only read images that are placed directly in the root of the ZIP archive. Nested archives and sub-folders inside the archive are not processed.
2. The URL must point directly to the image. Aspose.OCR for Node.js via C++ cannot extract images from HTML pages.  
   The library does not support authentication and can only work with public URLs.
{{% /alert %}}

## Recognition results

Recognition results are returned in the most popular data exchange formats:

Format    | Details
--------- | -------
**TEXT**  | Plain text.
**JSON**  | A popular open-standard format, widely used in software development and data exchange.
**XML**   | Extensible Markup Language, a universal format for most systems.
