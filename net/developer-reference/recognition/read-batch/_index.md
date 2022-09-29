---
weight: 60
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /net/batch-recognition/
title: Batch recognition
description: How to read text from a multiple raster images, folder, or ZIP archive.
keywords:
- read
- extract
- OCR
- recognize
- multiple
- batch
- archive
- folder
---

Aspose.OCR for .NET can read up to **20 images** in a single call. Images are be provided as a list of files, a folder, or a ZIP archive. Use [`RecognizeMultipleImages`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizemultipleimages/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This method supports JPEG, PNG, BMP, GIF, and single-page TIFF images.

{{% alert color="primary" %}}
Subfolders and nested archives are not supported.
{{% /alert %}}

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-image/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) objects, corresponding to each recognized image.

{{< tabs tabID="1" tabTotal="3" tabName1="Read multiple images" tabName2="Read images from ZIP achive" tabName3="Read images from folder" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Files list
List<string> images = new List<string>() {
	"page1.png",
	"page2.png",
	"page3.png"
};
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
// Extract text from images
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeMultipleImages(images, recognitionSettings);
// Save all pages as PDF
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeMultipleImages("images.zip", recognitionSettings);
// Save all pages as PDF
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeMultipleImages("C:/images/", recognitionSettings);
// Save all pages as PDF
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< /tabs >}}
