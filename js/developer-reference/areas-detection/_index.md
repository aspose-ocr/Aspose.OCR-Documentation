---
weight: 50
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/areas-detection/
title:  Document areas detection
description: How Aspose.OCR for JavaScript via C++ identifies and analyzes the structure and layout of the image during recognition.
keywords:
- structure
- region
- area
- blocks
- neural network
- algorithm
- mode
---

A scanned image or photograph of a text document may contain a large number of blocks of various content - text paragraphs, tables, illustrations, formulas, and the like. Detecting, ordering, and classifying areas of interest on a page is the cornerstone of successful and accurate OCR. This process is called _document areas detection_.

![Document structure analysis and recognition](structure-analysis.png)

Aspose.OCR for JavaScript via C++ offers several document areas detection models, allowing you to choose the one that works best for your specific content.

You can manually override the default document areas detection function if you are unhappy with the results or get unwanted artifacts. Document structure analysis model is specified in an optional `detect_areas_mode` parameter of [recognition settings](/ocr/javascript-cpp/settings/).

```javascript
// Prepare images
var source = Module.WasmAsposeOCRInput();
source.url = filename;
var content = new Module.WasmAsposeOCRInputs();
content.push_back(source);
// Recognize photos of curved book pages
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.detect_areas_mode = Module.DetectAreasMode.CURVED_TEXT;
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```

Aspose.OCR for JavaScript via C++ supports the following document structure analysis models:

Value                                | Numeric value | Description | Use cases
------------------------------------ | ------------- | ----------- | ---------
`Module.DetectAreasMode.NONE`        | 0             | Do not analyze document structure. Never disable automatic document areas detection when working with multi-paragraph and multi-column documents, tables, or photos. This can significantly reduce recognition accuracy. | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`Module.DetectAreasMode.DOCUMENT`    | 1             | Detect large blocks of text, such as paragraphs and columns. Optimal for multi-column documents with illustrations.<br />See [**Module.DetectAreasMode.DOCUMENT**](/ocr/javascript-cpp/areas-detection/document/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers<br />High-quality scans
`Module.DetectAreasMode.PHOTO`       | 2             | Finds small text blocks inside complex images.<br />See [**Module.DetectAreasMode.PHOTO**](/ocr/javascript-cpp/areas-detection/photo/) for additional details. | Driver’s licenses<br />Social security cards<br />Government and work IDs<br />Visas<br />Photos<br />Screenshots<br />Advertisements
`Module.DetectAreasMode.COMBINE`     | 3             | The combination of _Module.DetectAreasMode.DOCUMENT_ and _Module.DetectAreasMode.PHOTO_.<br />See [**Module.DetectAreasMode.COMBINE**](/ocr/javascript-cpp/areas-detection/combine/) for additional details. | Posters<br />Billboards<br />Datasheets<br />Random photos<br />Batch recognition
`Module.DetectAreasMode.TABLE`       | 4             | Detects cells in tabular structures.<br />See [**Module.DetectAreasMode.TABLE**](/ocr/javascript-cpp/areas-detection/table/) for additional details. | Tables<br />Invoices
`Module.DetectAreasMode.CURVED_TEXT` | 5             | Auto-straightens curved lines and finds text blocks inside the resulting image.<br />See [**Module.DetectAreasMode.CURVED_TEXT**](/ocr/javascript-cpp/areas-detection/curved_text/) for additional details. | Photos of books, magazine articles, and other curved pages.
