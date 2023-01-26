---
weight: 10
date: "2022-09-09"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/image/
feedback: OCRNET
aliases:
- /net/performing-ocr-on-an-image/
title: Extracting text from an image
description: How to read text from raster images in JPEG, PNG, TIFF, BMP, and GIF formats.
keywords:
- read
- extract
- OCR
- recognize
- image
- picture
---

To extract text from a raster image, use [`RecognizeImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimage/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This method supports JPEG, PNG, BMP, GIF, and single-page TIFF images.

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-image/).

Depending on the parameters, the method can either return a string with line breaks, or a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object that allows you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/net/spelling/), [get image regions](/ocr/net/image-regions-extract/) and [save](/ocr/net/save/) results in various formats.

{{< tabs tabID="1" tabTotal="3" tabName1="Read image from path" tabName2="Read image from memory" tabName3="Post-process recognition results" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
string result = recognitionEngine.RecognizeImage("source.png");
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
		string result = recognitionEngine.RecognizeImage(ms);
		Console.WriteLine(result);
	}
}
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Customize recognition
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
// Show non-critical recognition problems
foreach(string warning in result.Warnings)
{
	Console.WriteLine(warning);
}
// Get recognition results as JSON
string resultJson = result.GetJson();
```
{{< /tab >}}
{{< /tabs >}}
