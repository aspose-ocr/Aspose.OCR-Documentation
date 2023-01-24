---
weight: 20
date: "2023-01-23"
author: "Vladimir Lapin"
type: docs
url: /net/identify-problems/
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
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png",recognitionSettings);
foreach(string warning in result.Warnings)
{
	Console.WriteLine(warning);
}
```
