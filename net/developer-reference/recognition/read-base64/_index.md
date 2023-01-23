---
weight: 130
date: "2023-01-19"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/base64/
title: Extracting text from Base64 encoded image
description: How to read text from JPEG, PNG, TIFF, BMP, and GIF images provided as Base64 encoded string.
keywords:
- read
- extract
- OCR
- recognize
- image
- picture
- Base64
- encode
---

**Base64** is a popular encoding scheme that allows for representing any binary data as a plain text string. It is widely used for storing images in text-based formats such as JSON and XML, and for sending images over the web as query parameters.

Aspose.OCR for .NET can read text from JPEG, PNG, TIFF, BMP, and GIF images provided as a Base64 string. Processing is performed as a single operation without the need to first decode the string into binary code.

To extract text from a Base64-encoded image, use [`RecognizeImageFromBase64`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeimagefrombase64/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This method supports JPEG, PNG, BMP, GIF, and single-page TIFF images.

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-image/).

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object that allows you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/net/spelling/), [get image regions](/ocr/net/image-regions-extract/) and [save](/ocr/net/save/) results in various formats.

```csharp
string base64Image = "/9j/4QAYRXhpZgAASUkqAAgAAAAAAAAAAAAAAP ... yiGRH/9k=";
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImageFromBase64(base64Image, recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
