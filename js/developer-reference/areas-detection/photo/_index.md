---
weight: 20
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/areas-detection/photo/
title:  Module.DetectAreasMode.PHOTO
description: How Aspose.OCR for JavaScript via C++ determines the structure of a document using the Module.DetectAreasMode.PHOTO model.
keywords:
- structure
- region
- area
- blocks
- receipt
- screenshot
- photo
---

This model works best with sparse irregular text and low-quality photos. It detects smaller text areas in an image, such as individual words, phrases, or lines, and then positions them relative to each other in recognition results.

![Module.DetectAreasMode.PHOTO model](taa.png)

It is optimal for invoices, screenshots, driver's licenses, social security cards, government and work IDs, visas, math formulas, code snippets, and more. It can also detect small texts such as notes, signatures or stamps. In addition, it is well suited for reading smartphone photos and low-quality scans.

However, this model may be less efficient when dealing with large amounts of structured textual data, such as articles and books, and does not support multi-column layout. Try [**Module.DetectAreasMode.DOCUMENT**](/ocr/javascript-cpp/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection model:

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.detect_areas_mode = Module.DetectAreasMode.PHOTO;
```
