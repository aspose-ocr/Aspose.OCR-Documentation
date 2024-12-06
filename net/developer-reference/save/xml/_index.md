---
weight: 40
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/save-xml/
feedback: OCRNET
title: Getting recognition results as XML
description: Returning Aspose.OCR for .NET recognition results in XML format.
keywords:
- save
- result
- XML
- output
---

Aspose.OCR for .NET can return recognition results as XML - a universal data exchange and storage format. To get the results as XML, use [`GetXml`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/getxml/) method of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Show XML
string xml = results[0].GetXml();
Console.WriteLine(xml);
```
