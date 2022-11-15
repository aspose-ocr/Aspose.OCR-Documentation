---
weight: 50
date: "2022-11-15"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/curved_text/
title:  DetectAreasMode.CURVED_TEXT
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.CURVED_TEXT algorithm.
keywords:
- structure
- region
- area
- photo
- distort
- curve
---

When photographing pages of books and magazine articles, the cylindrical curvature of the page results in distortion of the image, causing the lines of text to curl. This 3D geometric distortion negatively affects recognition.

**DetectAreasMode.CURVED_TEXT** areas detection mode uses a specialized neural network that automatically tracks and rectifies curved lines of text. This greatly improves recognition accuracy and allows much more text to be recovered and extracted.

![Detecting and rectifying curved lines of text](curved_text.png)

However, this algorithm is less efficient and consumes more resources when dealing with perfectly straight images, such as a single scanned sheet of paper. Try [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) or [**DetectAreasMode.PHOTO**](/ocr/net/areas-detection/photo/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.CURVED_TEXT;
// Recognize image
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
