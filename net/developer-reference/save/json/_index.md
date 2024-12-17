---
weight: 30
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/save-json/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/get-ocr-result-as-json/
title: Getting recognition results as JSON
description: Returning Aspose.OCR for .NET recognition results in JSON format.
keywords:
- save
- result
- JSON
- output
---

Aspose.OCR for .NET can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get the results as JSON, use [`GetJson`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/getjson/) method of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object.

Set `isReadable` parameter of the method to `true` to get a JSON string in a human-readable format with line breaks and auto-indentation.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Show JSON
string json = results[0].GetJson(true);
Console.WriteLine(json);
```
