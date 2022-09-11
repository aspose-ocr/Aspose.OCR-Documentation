---
weight: 20
date: "2022-09-08"
author: "Vladimir Lapin"
type: docs
url: /net/recognize-single-line/
title: Recognize single line
description: How to read text from images containing a single line of text.
keywords:
- line
- simple
- fast
---

If an image contains a single line of text, it can be recognized in the fastest possible mode, without [automated corrections](/ocr/net/image-preprocessing/), [areas detection](/ocr/net/areas-detection/), and other resource-consuming steps.

To extract text from such images, use [`RecognizeLine`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeline/) method of of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class or enable `RecognizeSingleLine` property in [recognition settings](/ocr/net/recognition-settings/).

{{< tabs tabID="1" tabTotal="3" tabName1="Recognize image from path" tabName2="Recognize image from memory" tabName3="Recognition settings" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
string result = recognitionEngine.RecognizeLine("source.png");
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
		string result = recognitionEngine.RecognizeLine(ms);
		Console.WriteLine(result);
	}
}
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.RecognizeSingleLine = true;
string result = recognitionEngine.RecognizeImage("source.png");
Console.WriteLine(result);
```
{{< /tab >}}
{{< /tabs >}}

{{% alert color="primary" %}}
Please note that this method only works for images containing a single line of text! Using it on multi-line images will lead to incorrect recognition results.
{{% /alert %}}

## Performance impact

This method is about **7 times faster** than normal OCR and is highly recommended for batch processing large numbers of very simple images.

## Drawbacks

This recognition method only supports images in the following formats:

- GIF,
- 24-bit PNG,
- JPEG,
- BMP,
- single-page TIFF.

It also does not work with skewed images and does not support [recognition settings](/ocr/net/recognition-settings/). However, you can [preprocess](/ocr/net/image-preprocessing/) an image before sending it to the OCR engine.
