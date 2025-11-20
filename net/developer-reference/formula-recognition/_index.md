---
weight: 65
date: "2025-11-18"
author: "Anna Pylaieva"
type: docs
url: /net/formula-recognition/
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
- /net/recognition/formula/
feedback: OCRNET
title: Formula recognition
description: Extracting and recognizing formulas from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- formula
- extract
- OCR
- recognize
---

Reading text from any content in Aspose.OCR for .NET is as easy as calling a universal [`Aspose.OCR.AsposeOcr.Recognize`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognize/) method.

This method takes [`OcrInput` object](/ocr/net/ocrinput/) and optional [recognition settings](/ocr/net/recognition-settings-common/).

Recognition results are returned as a list of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, that allow you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/net/spelling/), [get image regions](/ocr/net/image-regions-extract/) and [save](/ocr/net/save/) results in various formats.

Aspose.OCR for .NET now provides a dedicated API for detecting and recognizing mathematical formulas in images, scanned documents, screenshots, or photos.
To extract formula text, simply call the universal [`Aspose.OCR.AsposeOcr.RecognizeFormula`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeformula/) method.

This method accepts an `OcrInput` object and optional recognition settings.
Internally, formula detection uses the [`DetectAreasMode.FORMULA`](https://reference.aspose.com/ocr/net/aspose.ocr/detectareasmode/) mode to locate mathematical expressions before recognition.

Recognition results are returned as a list of `Aspose.OCR.RecognitionResult` objects. Each result contains extracted formula text, detected regions, and allows exporting to various formats.

## DetectAreasMode.FORMULA

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Configure recognition settings for formulas
Aspose.OCR.RecognitionSettings settings = new Aspose.OCR.RecognitionSettings();
settings.DetectAreasMode = Aspose.OCR.DetectAreasMode.FORMULA;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Cancelling recognition

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");

// Recognize formulas with areas detection
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizeFormula(input, true);
// Parameter bool detectAreas - if set to true, automatically detects and isolates formula regions before performing recognition. If false, processes the entire image as a formula.

foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
