---
weight: 20
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/identify-problems/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Identifying recognition problems
description: How to identify non-fatal errors that occurred during recognition.
keywords:
- error
- issue
- problem
- catch
---

Non-fatal recognition errors are stored as a list of strings in the `Warnings` property of the [recognition result](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/).

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Output warnings
foreach(string warning in result[0].Warnings)
{
	Console.WriteLine(warning);
}
```
