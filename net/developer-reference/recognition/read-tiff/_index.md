---
weight: 30
date: "2022-09-09"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/tiff/
aliases:
- /net/recognize-multipage-tiff/
title: Extracting text from multi-page TIFF
description: How to read text from multi-page TIFF images.
keywords:
- read
- extract
- OCR
- recognize
- TIF
- TIFF
- pages
- multiple
---

To extract text from a multi-page TIFF image, use [`RecognizeTiff`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizetiff/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-document/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, corresponding to each recognized page.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeTiff("source.tiff", recognitionSettings);
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
