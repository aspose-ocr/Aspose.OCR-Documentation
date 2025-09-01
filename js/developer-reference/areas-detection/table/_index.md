---
weight: 40
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/areas-detection/table/
title:  Module.DetectAreasMode.TABLE
description: How Aspose.OCR for JavaScript via C++ determines the structure of a document using the Module.DetectAreasMode.TABLE algorithm.
keywords:
- structure
- region
- area
- table
- cell
- row
---

When this model is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection model is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**Module.DetectAreasMode.DOCUMENT**](/ocr/javascript-cpp/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.detect_areas_mode = Module.DetectAreasMode.TABLE;
```
