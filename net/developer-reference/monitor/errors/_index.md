---
weight: 20
date: "2023-03-09"
author: "Vladimir Lapin"
type: docs
url: /net/identify-problems/
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
