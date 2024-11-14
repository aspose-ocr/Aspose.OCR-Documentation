---
weight: 40
date: "2024-11-13"
author: "Vladimir Lapin"
type: docs
url: /java/areas-detection/table/
feedback: OCRJAVA
title:  DetectAreasMode.TABLE
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.TABLE algorithm.
keywords:
- structure
- region
- area
- table
- cell
- row
---

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/java/modules/) advanced OCR models (**aspose-ocr-advanced-recognition-v1**) in your project.
{{% /alert %}}

When this mode is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection mode is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**DetectAreasMode.DOCUMENT**](/ocr/java/areas-detection/multicolumn/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.TABLE);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.add("image.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
System.out.println("Recognition result:\n" + results[0].recognitionText + "\n\n");
```
