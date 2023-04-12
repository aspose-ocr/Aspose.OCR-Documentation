---
weight: 10
date: "2023-04-08"
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

Aspose.OCR can work in the fastest recognition mode that consumes minimum possible resources using [`RecognizeImageFast`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimagefast/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

Unlike [regular recognition methods](/ocr/net/recognition/), this method can only read a single image and returns a string with extracted text.

{{< tabs tabID="1" tabTotal="2" tabName1="Recognize image from path" tabName2="Recognize image from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
string result = recognitionEngine.RecognizeImageFast("source.png");
Console.WriteLine(result);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("source.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		string result = recognitionEngine.RecognizeImageFast(ms);
		Console.WriteLine(result);
	}
}
```
{{< /tab >}}
{{< /tabs >}}

## Performance impact

This method is about **twice as fast** as [regular recognition](/ocr/net/recognition/).

## Drawbacks

- This method only supports PNG, JPEG, BMP, GIF, and single-page TIFF images.
- This recognition method only works with high-quality scans without skew or distortion. However, you can [preprocess](/ocr/net/image-processing/#previewing-and-saving-processed-images) an image before sending it to the OCR engine.
- Fast recognition cannot be customized with [recognition settings](/ocr/net/recognition-settings/).
