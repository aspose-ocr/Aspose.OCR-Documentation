---
weight: 30
date: "2022-09-08"
author: "Vladimir Lapin"
type: docs
url: /net/multithreading/
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
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
// Limit resource usage to 2 threads
recognitionSettings.ThreadsCount = 2;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
