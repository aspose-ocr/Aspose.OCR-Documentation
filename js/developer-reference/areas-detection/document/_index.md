---
weight: 10
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/areas-detection/document/
title: Module.DetectAreasMode.DOCUMENT
description: How Aspose.OCR for JavaScript via C++ determines the structure of a document using the Module.DetectAreasMode.DOCUMENT model.
keywords:
- structure
- region
- area
- blocks
- article
- colum
- document
---

This model works best with large amounts of structured text such as scanned contracts, book pages, articles, newspapers, and the like. It breaks content into larger blocks, such as paragraphs and columns. These blocks are then analyzed, read and combined into recognition results.

![Module.DetectAreasMode.DOCUMENT model](dsr.png)

_\*The example article is Copyright &copy; 2016 CLINICS, distributed under the terms of the Creative Commons license._

However, it may not be suitable for analyzing photographs and small amounts of irregular text - try [**Module.DetectAreasMode.PHOTO**](/ocr/javascript-cpp/areas-detection/photo/) instead.

## Example

The following code sample demonstrates how to use this document areas detection model:

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.detect_areas_mode = Module.DetectAreasMode.DOCUMENT;
```
