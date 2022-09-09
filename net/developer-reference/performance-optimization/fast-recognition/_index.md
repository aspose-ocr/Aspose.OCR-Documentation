---
weight: 10
date: "2022-09-08"
author: "Vladimir Lapin"
type: docs
url: /net/fast-recognition/
title: Fast recognition
description: Extract text from high-quality scans using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Very simple and clear images, such as high-quality scans, do not require [automated corrections](/ocr/net/image-preprocessing/) and [areas detection](/ocr/net/areas-detection/).

Aspose.OCR can work in the fastest recognition mode that consumes minimum possible resources using [`RecognizeImageFast`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimagefast/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

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

This method is about **twice as fast** as regular recognition and is recommended for public web applications and mobile devices.

## Drawbacks

This recognition mode does not work with skewed images and does not support [recognition settings](/ocr/net/recognition-settings/). However, you can [preprocess](/ocr/net/image-preprocessing/) an image before sending it to the OCR engine.
