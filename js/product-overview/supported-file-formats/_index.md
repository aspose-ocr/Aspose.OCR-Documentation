---
weight: 20
date: "2023-11-24"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/supported-file-formats/
title: Supported file formats
description: File formats for images and recognition results supported by Aspose.OCR for JavaScript via C++.
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

Aspose.OCR for JavaScript via C++ can recognize any file you get from a scanner or camera:

Extension             | Details
--------------------- | -------
**.JPG** or **.JPEG** | JPEG, the most popular format for smartphone photos.
**.PNG**              | Portable Network Graphics. Supports 24-bit images with transparency.
**.TIFF** or **.TIF** | Tag Image File Format, commonly used for high quality scanning. Multi-page TIFF images are fully supported.
**.BMP**              | Bitmap image file.
**.ZIP**              | All JPEG, PNG, TIFF and BMP images inside the archive.

{{% alert color="caution" %}}
Aspose.OCR for JavaScript via C++ engine can only read images that are placed directly in the root of the ZIP archive. Nested archives and sub-folders inside the archive are not processed.
{{% /alert %}}


## Recognition results

Recognition results are returned in the most popular document and data exchange formats:

Format    | Details
--------- | -------
**.TXT**  | Plain text
**.HTML** | Web page
**.RTF**  | A universal format for exchanging rich text documents between different word processing programs
**.DOCX** | Microsoft Word document
**.XLSX** | Microsoft Excel spreadsheet
**.PDF**  | Portable Document Format
**.EPUB** | Popular e-book file format
**JSON**  | A popular open-standard format, widely used in software development and data exchange
**XML**   | Extensible Markup Language, a universal format for most systems
