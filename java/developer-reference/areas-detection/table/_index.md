---
weight: 40
date: "2022-11-15"
author: "Vladimir Lapin"
type: docs
url: /java/areas-detection/table/
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

When this mode is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection mode is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**DetectAreasMode.DOCUMENT**](/ocr/java/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.TABLE);
// Convert image to table
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
