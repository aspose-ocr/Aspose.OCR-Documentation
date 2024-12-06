---
weight: 10
date: "2024-10-18"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/multicolumn/
aliases:
- /net/areas-detection/document/
feedback: OCRNET
title: DetectAreasMode.MULTICOLUMN
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.MULTICOLUMN algorithm.
keywords:
- structure
- region
- area
- blocks
- article
- colum
- document
---

This algorithm is optimized for handling large amounts of text arranged in multiple columns, such as scanned contracts, book pages, articles, and newspapers. Unlike other content detection methods that treat text as a single column, this approach processes each column individually.

![DetectAreasMode.MULTICOLUMN algorithm](dsr.png)

_\*The example article is Copyright &copy; 2016 CLINICS, distributed under the terms of the Creative Commons license._

However, it may not be suitable for analyzing photographs and small amounts of irregular text - try [**DetectAreasMode.UNIVERSAL**](/ocr/net/areas-detection/universal/) instead.

## Example

The following code sample demonstrates how to use this content areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.MULTICOLUMN;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
