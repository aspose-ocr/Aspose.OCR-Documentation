---
weight: 30
date: "2023-04-09"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/combine/
feedback: OCRNET
title:  DetectAreasMode.COMBINE
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.COMBINE algorithm.
keywords:
- structure
- region
- area
- blocks
- photo
- universal
---

The combination of [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) and [**DetectAreasMode.PHOTO**](/ocr/net/areas-detection/photo/), which can extract as much text from an image as possible. The OCR engine detects large blocks of text (such as paragraphs and columns), while the remaining content is analyzed by **DetectAreasMode.PHOTO** algorithm.

This allows you to handle even the most complex cases like posters, billboards, or random photos. However, it can take a little longer and may be less efficient than the specialized algorithms. Try one of the [dedicated area detection methods](/ocr/net/areas-detection/#area-detection-modes) if you are sure of the content type.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.COMBINE;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
