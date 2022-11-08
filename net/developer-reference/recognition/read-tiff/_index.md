---
weight: 30
date: "2022-11-07"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/tiff/
aliases:
- /net/recognize-multipage-tiff/
title: Extracting text from multi-page TIFF
description: How to read text from multi-page TIFF images.
keywords:
- read
- extract
- OCR
- recognize
- TIF
- TIFF
- pages
- multiple
---

To extract text from a multi-page TIFF image, use [`RecognizeTiff`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizetiff/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-document/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, corresponding to each recognized page.

{{< tabs tabID="1" tabTotal="2" tabName1="Read TIFF from path" tabName2="Read TIFF from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeTiff("source.tiff", recognitionSettings);
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("source.tiff", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
		recognitionSettings.Language = Aspose.OCR.Language.Ukr;
		List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeTiff(ms, recognitionSettings);
		Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
