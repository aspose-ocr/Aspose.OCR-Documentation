---
weight: 70
date: "2025-01-22"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
aliases:
- /net/recognition/image/
- /net/recognition/pdf/
- /net/recognition/tiff/
- /net/recognition/djvu/
- /net/recognition/url/
- /net/batch-recognition/
- /net/recognition/pixel/
- /net/recognition/base64/
- /net/recognition/read-text-in-wild/
feedback: OCRNET
title: Recognition
description: Extracting text from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- read
- extract
- OCR
- recognize
---

Reading text from any content in Aspose.OCR for .NET is as easy as calling a universal [`Aspose.OCR.AsposeOcr.Recognize`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognize/) method.

This method takes [`OcrInput` object](/ocr/net/ocrinput/) and optional [recognition settings](/ocr/net/recognition-settings-common/).

Recognition results are returned as a list of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, that allow you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/net/spelling/), [get image regions](/ocr/net/image-regions-extract/) and [save](/ocr/net/save/) results in various formats.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Set recognition language
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Cancelling recognition

Aspose.OCR for .NET allows you to forcibly cancel the recognition process either manually or automatically after the specified number of milliseconds. The cancellation process is based on the standardized [`System.Threading.CancellationTokenSource`](https://learn.microsoft.com/en-us/dotnet/api/system.threading.cancellationtokensource.cancel) object and flows.

The recognition is immediately cancelled regardless of the number of [threads](/ocr/net/multithreading/).

{{% alert color="caution" %}}
Cancelling the recognition means that all recognition results are lost, even the ones which are already available at the moment of cancellation.
{{% /alert %}}

```csharp
// Set automatic cancellation after 20 seconds (20,000ms)
CancellationTokenSource cancellationTokenSource  = new CancellationTokenSource();
cancellationTokenSource.CancelAfter(20000);
// Initialize Aspose.OCR for .NET recognition API
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add scanned PDF to recognition batch
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.PDF);
input.Add("large.pdf");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, null, cancellationTokenSource.Token);
```
