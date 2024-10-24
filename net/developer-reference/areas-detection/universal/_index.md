---
weight: 20
date: "2024-10-18"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/universal/
aliases:
- /net/areas-detection/photo/
- /net/areas-detection/combine/
- /net/areas-detection/text-in-wild/
feedback: OCRNET
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

This algorithm works best with sparse irregular text, including street photos and screenshots. It detects smaller text areas in an image, such as individual words, phrases, or lines, and then positions them relative to each other in recognition results.

![DetectAreasMode.UNIVERSAL algorithm](taa.png)

It is optimal for photos (including street photos), screenshots, driver's licenses, social security cards, government and work IDs, visas, math formulas, code snippets, price tags, and much more. It can also detect small texts such as notes, signatures or stamps. In addition, it is well suited for reading smartphone photos and low-quality scans. In general, it is a versatile option for most images.

However, this algorithm is inefficient when dealing with multi-column layouts and tables. Try [**DetectAreasMode.MULTICOLUMN**](/ocr/net/areas-detection/multicolumn/) or [**DetectAreasMode.TABLE**](/ocr/net/areas-detection/table/) instead.

## Example

The following code sample demonstrates how to use this content areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.UNIVERSAL;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
