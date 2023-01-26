---
weight: 10
date: "2023-01-23"
author: "Vladimir Lapin"
type: docs
url: /net/track-progress/
feedback: OCRNET
title: Tracking recognition progress
description: How to track the process of batch recognition and text extraction from multipage documents.
keywords:
- process
- batch
- pages
- progress
- event
---

Aspose.OCR for .NET allows you to [batch process](/ocr/net/batch-recognition/) multiple images, process all images from archives and folders, and extract texts from [multi-page documents](/ocr/net/recognition/). These operations can take a significant amount of time and may cause the end user to think that recognition is stuck due to some error.

The library exposes the [`Aspose.OCR.AsposeOcr.OcrProgress`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/ocrprogress/) event, which is raised when a page or file from a batch is processed. You can implement an event listener and report progress even in case of [multi-threaded](/ocr/net/multithreading/) recognition.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
recognitionEngine.OcrProgress += (Aspose.OCR.Models.Events.OcrPageRecognizeEventsArgs e) => {
	Console.WriteLine($"Read page: {e.CurrentPage} | image: {e.CurrentImage} | time taken: {e.Duration.TotalSeconds} sec");
};
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizePdf("source.pdf", recognitionSettings);
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.json", Aspose.OCR.SaveFormat.Json, results);
```

For each page or file, the following information is reported:

Property | Type | Description
-------- | ---- | -----------
`CurrentImage` | `int` | The ordinal number of the image.
`CurrentPage` | `int` | The ordinal number of the page in a multi-page image or document: [TIFF](/ocr/net/recognition/tiff/), [DjVu](/ocr/net/recognition/djvu/) or [PDF](/ocr/net/recognition/pdf/).
`Duration` | `TimeSpan` | The time interval from the start of image or page recognition until it is fully recognized.
