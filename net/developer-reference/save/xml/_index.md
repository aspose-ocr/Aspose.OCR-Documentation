---
weight: 40
date: "2022-09-06"
author: "Vladimir Lapin"
type: docs
url: /net/save-xml/
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
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
string xml = result.GetXml();
Console.WriteLine(xml);
```
