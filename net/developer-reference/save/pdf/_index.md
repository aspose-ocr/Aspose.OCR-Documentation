---
weight: 11
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/save-searchable-pdf/
feedback: OCRNET
aliases:
- /net/save-ocr-result-as-multipage-document/
title: Saving recognition results as a searchable PDF
description: Saving Aspose.OCR for .NET recognition results as a searchable and indexable PDF document.
keywords:
- save
- result
- file
- PDF
---

To convert recognition results into a searchable and indexable PDF document, use `SaveMultipageDocument` method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition. Provide `Aspose.OCR.SaveFormat.Pdf` as `saveFormat` parameter.

The resulting PDF will have original images in the background and a transparent text overlay that can be searched, selected and copied.

You can optionally enable [automatic spelling corrections](/ocr/net/automatic-spelling-correction/) for recognition results and provide a [custom dictionary](/ocr/net/dictionaries/).

{{< tabs tabID="1" tabTotal="2" tabName1="Save PDF to file" tabName2="Write PDF to memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input);
// Save results
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input);
// Save results
using(MemoryStream ms = new MemoryStream())
{
	Aspose.OCR.AsposeOcr.SaveMultipageDocument(ms, Aspose.OCR.SaveFormat.Pdf, results);
}
```
{{< /tab >}}
{{< /tabs >}}
