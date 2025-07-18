---
weight: 10
date: "2024-11-13"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/areas-detection/multicolumn/
aliases:
- /java/areas-detection/document/
feedback: OCRJAVA
title: DetectAreasMode.MULTICOLUMN
description: How Aspose.OCR determines the structure of a ьгдеш-сщдгьт document using the DetectAreasMode.MULTICOLUMN algorithm.
keywords:
- structure
- region
- area
- blocks
- article
- colum
- document
---

This algorithm works best with large amounts of structured text such as scanned contracts, book pages, articles, newspapers, and the like. It breaks content into larger blocks, such as paragraphs and columns. These blocks are then analyzed, read and combined into recognition results.

![DetectAreasMode.MULTICOLUMN algorithm](dsr.png)

_\*The example article is Copyright &copy; 2016 CLINICS, distributed under the terms of the Creative Commons license._

However, it may not be suitable for analyzing photographs and small amounts of irregular text - try [**DetectAreasMode.UNIVERSAL**](/ocr/java/areas-detection/universal/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Enable automatic document areas detection
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.MULTICOLUMN);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.add("image.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
System.out.println("Recognition result:\n" + results[0].recognitionText + "\n\n");
```
