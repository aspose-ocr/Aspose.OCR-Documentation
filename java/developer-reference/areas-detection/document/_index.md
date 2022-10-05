---
weight: 10
date: "2022-09-28"
author: "Vladimir Lapin"
type: docs
url: /java/areas-detection/document/
title: DetectAreasMode.DOCUMENT
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.DOCUMENT algorithm.
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

![DetectAreasMode.DOCUMENT algorithm](dsr.png)

_\*The example article is Copyright &copy; 2016 CLINICS, distributed under the terms of the Creative Commons license._

However, it may not be suitable for analyzing photographs and small amounts of irregular text - try [**DetectAreasMode.PHOTO**](/ocr/java/areas-detection/photo/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Enable automatic document areas detection
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.DOCUMENT);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
