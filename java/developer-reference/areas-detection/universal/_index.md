---
weight: 20
date: "2024-11-13"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/areas-detection/photo/
aliases:
- /java/areas-detection/photo/
- /java/areas-detection/combine/
- /java/areas-detection/text-in-wild/
feedback: OCRJAVA
title:  DetectAreasMode.UNIVERSAL
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.UNIVERSAL algorithm.
keywords:
- structure
- region
- area
- blocks
- receipt
- screenshot
- photo
---

This algorithm works best with sparse irregular text and low-quality photos. It detects smaller text areas in an image, such as individual words, phrases, or lines, and then positions them relative to each other in recognition results.

![DetectAreasMode.UNIVERSAL algorithm](taa.png)

It is optimal for invoices, screenshots, driver's licenses, social security cards, government and work IDs, visas, math formulas, code snippets, and more. It can also detect small texts such as notes, signatures or stamps. In addition, it is well suited for reading smartphone photos and low-quality scans.

However, this algorithm may be less efficient when dealing with large amounts of structured textual data, such as articles and books, and does not support multi-column layout. Try [**DetectAreasMode.MULTICOLUMN**](/ocr/java/areas-detection/multicolumn/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Enable automatic document areas detection
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.UNIVERSAL);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.add("image.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
System.out.println("Recognition result:\n" + results[0].recognitionText + "\n\n");
```
