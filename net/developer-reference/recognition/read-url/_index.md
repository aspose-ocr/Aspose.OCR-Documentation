---
weight: 50
date: "2022-09-09"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/url/
aliases:
- /net/performing-ocr-on-an-image-from-url/
title: Extracting text from URL
description: How to read text from raster images in JPEG, PNG, TIFF, BMP, and GIF formats provided by web links.
keywords:
- read
- extract
- OCR
- recognize
- image
- picture
---

Aspose.OCE for .NET can recognize images hosted on websites without downloading them to your computer. The only thing you need is the URL. Use [`RecognizeImageFromUri`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimagefromuri/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This method supports JPEG, PNG, BMP, GIF, and single-page TIFF images.

{{% alert color="primary" %}}
This method does not support authentication and can only work with public links.
{{% /alert %}}

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-image/).

Depending on the parameters, the method can either return a string with line breaks, or a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object that allows you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/net/spelling/), [get image regions](/ocr/net/image-regions-extract/) and [save](/ocr/net/save/) results in various formats.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AutoDenoising = true;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImageFromUri("https://upload.wikimedia.org/wikipedia/commons/e/e4/Biggle_horse_book_%28Page_45%29_BHL23865068.jpg", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
