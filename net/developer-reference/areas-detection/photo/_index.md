---
weight: 20
date: "2023-04-09"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/photo/
feedback: OCRNET
title:  DetectAreasMode.PHOTO
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.PHOTO algorithm.
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

![DetectAreasMode.PHOTO algorithm](taa.png)

It is optimal for invoices, screenshots, driver's licenses, social security cards, government and work IDs, visas, math formulas, code snippets, and more. It can also detect small texts such as notes, signatures or stamps. In addition, it is well suited for reading smartphone photos and low-quality scans.

However, this algorithm may be less efficient when dealing with large amounts of structured textual data, such as articles and books, and does not support multi-column layout. Try [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.PHOTO;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
