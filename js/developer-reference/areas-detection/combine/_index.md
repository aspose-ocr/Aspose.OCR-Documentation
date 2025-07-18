---
weight: 30
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/areas-detection/combine/
title:  Module.DetectAreasMode.COMBINE
description: How Aspose.OCR for JavaScript via C++ determines the structure of a document using the Module.DetectAreasMode.COMBINE model.
keywords:
- structure
- region
- area
- blocks
- photo
- universal
---

The combination of [**Module.DetectAreasMode.DOCUMENT**](/ocr/javascript-cpp/areas-detection/document/) and [**Module.DetectAreasMode.PHOTO**](/ocr/javascript-cpp/areas-detection/photo/), which can extract as much text from an image as possible. The OCR engine detects large blocks of text (such as paragraphs and columns), while the remaining content is analyzed by **Module.DetectAreasMode.PHOTO** model.

This allows you to handle even the most complex cases like posters, billboards, or random photos. However, it can take a little longer and may be less efficient than the specialized models. Try one of the [dedicated area detection models](/ocr/javascript-cpp/areas-detection/#area-detection-modes) if you are sure of the content type.

## Example

The following code sample demonstrates how to use this document areas detection model:

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.detect_areas_mode = Module.DetectAreasMode.COMBINE;
```
