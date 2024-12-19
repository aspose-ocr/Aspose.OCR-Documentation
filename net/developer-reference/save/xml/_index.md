---
weight: 40
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/save-xml/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
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
