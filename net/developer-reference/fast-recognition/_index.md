---
weight: 60
date: "2022-08-25"
author: "Vladimir Lapin"
type: docs
url: /net/fast-recognition/
title: Fast recognition
description: Automatic or manual actions for formatting an image before sending it for recognition.
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

This mode is approximately twice as fast as regular recognition and is recommended for public web applications and mobile devices.
