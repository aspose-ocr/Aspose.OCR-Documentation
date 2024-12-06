---
weight: 30
date: "2023-09-13"
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

Aspose.OCR for .NET allows you to limit the number of threads used by the recognition engine. Decreasing the number of threads may slow down the recognition speed, but will allow you to reserve some resources for other processes such as the parallel image processing, web server, database management system, or background data analysis.

{{% alert color="primary" %}}
Regardless of the setting, the number of threads cannot exceed the total number of CPU cores/threads.
{{% /alert %}}

To set the number of threads, use `ThreadsCount` parameter of the [recognition settings](/ocr/net/settings/):

Value | Behavior
----- | --------
_Not set_ | The OCR engine will use all CPU cores/threads.
0 | The OCR engine will use all CPU cores/threads.
1 | OCR will be performed on the application's main thread.
_More than 1_ | The OCR engine will use the number of threads provided, but not more than the total number of CPU cores/threads. Read [How it works](#how-it-works) for technical details.

## How it works

Multithreading works differently depending on the number of images in the [recognition batch](/ocr/net/ocrinput/).

### Recognizing one image

Applies to:

- recognition of a single image;
- recognition of a single-page PDF.

Aspose.OCR for .NET will use the provided number of threads to recognize blocks of text found on the image/page in parallel.


### Recognizing multiple files/pages

Applies to:

- recognition of several images;
- recognition of multi-page PDF documents;
- recognition of multi-page TIFF images;
- recognition of DjVu files;
- bulk recognition of all images in a folder;
- bulk recognition of all images in a ZIP archive.

Each image from the batch is processed in **one** separate thread. If more than one thread is specified in `ThreadsCount` parameter, images are recognized in parallel. The number of images processed simultaneously cannot exceed the value of `ThreadsCount` [recognition settings](/ocr/net/settings/) or the total number of CPU cores/threads (whichever is less). Image regions are always recognized one by one.

{{% alert color="info" %}}
Since each image in a batch is recognized in one thread, the maximum number of threads used by the Aspose.OCR engine will not exceed the total number of images regardless of the `ThreadsCount` setting.
{{% /alert %}}

## Example

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
input.Add("source3.png");
input.Add("source4.jpg");
// Limit resource usage to 2 threads
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.ThreadsCount = 2;
// Recognize batch by 2 images in parallel
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
