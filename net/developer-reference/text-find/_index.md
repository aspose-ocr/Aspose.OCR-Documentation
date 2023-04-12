---
weight: 110
date: "2023-01-20"
author: "Vladimir Lapin"
type: docs
url: /net/find-text/
feedback: OCRNET
title: Finding text in an image
description: How to determine if an image contains provided text.
keywords:
- find
- detect
- identify
- locate
- text
- string
---

Aspose.OCR for .NET makes searching for text in images as easy as finding the text fragment in a string. In a single line of code, you can search for a case-sensitive or case-insensitive string, and even validate an image text against a pattern.

To search for a text in an image, use [`ImageHasText`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/imagehastext/) method of [`AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. The method either takes a text fragment or a regular expression and returns `true` if the text is found or `false` if not.

`ImageHasText` method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-image/).

{{< tabs tabID="1" tabTotal="2" tabName1="Read image from path" tabName2="Read image from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
if(recognitionEngine.ImageHasText("source.png", "Aspose", recognitionSettings))
{
	Console.WriteLine(@"The image contains the word ""Aspose""");
}
else
{
	Console.WriteLine(@"The image doesn't contain the word ""Aspose""");
}
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Regex rx = new Regex(@"Aspose\.O(C|M)R", RegexOptions.IgnoreCase);
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
if(recognitionEngine.ImageHasText("source.png", rx, recognitionSettings))
{
	Console.WriteLine(@"The image contains ""Aspose.OCR"" or ""Aspose.OMR""");
}
else
{
	Console.WriteLine(@"The image doesn't contain ""Aspose.OCR"" or ""Aspose.OMR""");
}
```
{{< /tab >}}
{{< /tabs >}}
