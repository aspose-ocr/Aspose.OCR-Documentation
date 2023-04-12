---
weight: 30
date: "2023-04-08"
author: "Vladimir Lapin"
type: docs
url: /net/multithreading/
feedback: OCRNET
aliases:
- /net/multithreading-support-in-recognition/
title: Multithreading support
description: Optimize the resource usage by limiting the number of threads used by Aspose.OCR for .NET recognition engine.
keywords:
- thread
- cpu
- core
---

Aspose.OCR for .NET allows you to limit the number of threads used by the recognition engine. This may slow down the recognition speed, but will allow you to reserve some resources for other processes such as the parallel image processing, web server, database management system, or background data analysis.

To set the number of threads, use [`ThreadsCount`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/threadscount/) parameter of the [`RecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) object.

- If you specify `0` or do not set this parameter, the recognition engine will use all CPU cores.
- If you specify `1`, recognition will be performed on the application's main thread.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Limit resource usage to 2 threads
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.ThreadsCount = 2;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
