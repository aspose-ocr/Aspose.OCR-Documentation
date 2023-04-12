---
weight: 70
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/
aliases:
- /net/recognition/image/
- /net/recognition/pdf/
- /net/recognition/tiff/
- /net/recognition/djvu/
- /net/recognition/url/
- /net/batch-recognition/
- /net/recognition/pixel/
- /net/recognition/base64/
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

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for .NET 23.3.1, this method replaces `RecognizeImage`, `RecognizePdf`, `RecognizeTiff`, `RecognizeDjvu`, `RecognizeImageFromUri`, `RecognizeMultipleImages`, and `RecognizeImageFromBase64` recognition methods.
{{% /alert %}}

## Example

The following code example shows how to extract text from multiple images:

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
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
