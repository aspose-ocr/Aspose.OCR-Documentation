---
weight: 20
date: "2023-04-08"
author: "Vladimir Lapin"
type: docs
url: /net/recognize-single-line/
feedback: OCRNET
title: Recognize single line
description: How to read text from images containing a single line of text.
keywords:
- line
- simple
- fast
---

If an image contains a single line of text, it can be recognized in the fastest possible mode, without [automated corrections](/ocr/net/image-preprocessing/), [areas detection](/ocr/net/areas-detection/), and other resource-consuming steps. To extract text from such images, use [`Aspose.OCR.AsposeOcr.RecognizeLines`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizelines/) method or enable `RecognizeSingleLine` property in [recognition settings](/ocr/net/recognition-settings/).

This method takes [`OcrInput` object](/ocr/net/ocrinput/) and optional [recognition settings](/ocr/net/recognition-settings-common/).

Recognition results are returned as a list of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, that allow you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/net/spelling/), [get image regions](/ocr/net/image-regions-extract/) and [save](/ocr/net/save/) results in various formats.

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for .NET 23.3.1, this method replaces `Aspose.OCR.AsposeOcr.RecognizeLine` recognition method.
{{% /alert %}}

## Example

The following code example shows how to extract text from a single-line image:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add a single-line image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set recognition language
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeLines(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Performance impact

This method is about **7 times faster** than normal OCR and is highly recommended for batch processing large numbers of very simple images.

## Drawbacks

This method only works for images which contain a single line of text! Using it on multi-line images will lead to incorrect recognition results.
