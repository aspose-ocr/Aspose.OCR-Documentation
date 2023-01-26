---
weight: 30
date: "2022-09-06"
author: "Vladimir Lapin"
type: docs
url: /net/save-json/
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
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
string json = result.GetJson(true);
Console.WriteLine(json);
```
