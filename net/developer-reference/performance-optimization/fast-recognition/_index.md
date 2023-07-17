---
weight: 10
date: "2023-05-18"
author: "Vladimir Lapin"
type: docs
url: /net/fast-recognition/
feedback: OCRNET
title: Fast recognition
description: How to read text from high-quality images using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Aspose.OCR can work in the fastest recognition mode that consumes minimum possible resources using [`RecognizeFast`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizefast/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a list of strings, one string per image.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput images = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
images.Add("source1.png");
images.Add("source2.png");
// Fast recognize images
List<string> results = recognitionEngine.RecognizeFast(images);
foreach(string result in results)
{
	Console.WriteLine(result);
}
```

## Performance impact

This method is about **twice as fast** as [regular recognition](/ocr/net/recognition/).

## Drawbacks

- This recognition method only works with high-quality scans without skew or distortion. However, you can [preprocess](/ocr/net/image-processing/#previewing-and-saving-processed-images) an image before sending it to the OCR engine.
- Fast recognition cannot be customized with [recognition settings](/ocr/net/recognition-settings/).
