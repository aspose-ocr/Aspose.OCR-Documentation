---
weight: 20
date: "2022-09-09"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/pdf/
aliases:
- /net/recognize-scanned-pdf/
title: Extracting text from PDF document
description: How to read text from a scanned PDF and convert scanned documents into searchable PDF files.
keywords:
- read
- extract
- OCR
- recognize
- PDF
- scan
- document
---

To extract text from a PDF document that consists of scanned images without searchable text, use [`RecognizePdf`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizepdf/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-document/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, corresponding to each recognized page.

{{< tabs tabID="1" tabTotal="2" tabName1="Read PDF from path" tabName2="Read PDF from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizePdf("source.pdf", recognitionSettings);
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.json", Aspose.OCR.SaveFormat.Json, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("source.pdf", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizePdf(ms, recognitionSettings);
		Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.json", Aspose.OCR.SaveFormat.Json, results);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
