---
weight: 10
date: "2023-03-09"
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

Aspose.OCR for .NET exposes the [`Aspose.OCR.AsposeOcr.OcrProgress`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/ocrprogress/) event, which is raised when a page or file from a batch is processed. You can implement an event listener and report progress even in case of [multi-threaded](/ocr/net/multithreading/) recognition.

The event handler not only reports information about the processed file during [batch processing](/ocr/net/batch-recognition/) of multiple images, but also reports information about the stage of recognition/processing of each individual image.


```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Event handler
recognitionEngine.OcrProgress += (Aspose.OCR.Models.Events.OcrPageRecognizeEventsArgs e) => {
	Console.WriteLine($"Read page: {e.CurrentPage} | image: {e.CurrentImage} | time taken: {e.Duration.TotalSeconds} sec");
};
// Recognize images
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input);
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.json", Aspose.OCR.SaveFormat.Json, results);
```

For each page or file, the following information is reported:

Property | Type | Description
-------- | ---- | -----------
`FileName` | `string` | The name of the file that is currently being recognized.
`CurrentImage` | `int` | The ordinal number of the image.
`CurrentPage` | `int` | The ordinal number of the page in a batch or a multi-page image/document.
`Duration` | `TimeSpan` | The time interval from the start of image or page recognition until it is fully recognized.
`OperationName` | `string` | Progress stage of a single image recognition.
