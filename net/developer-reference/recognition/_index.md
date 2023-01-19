---
weight: 60
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/
title: Recognition
description: Extracting text from images, web links, PDF documents, and DjVu files.
keywords:
- read
- extract
- OCR
- recognize
---

Aspose.OCR for .NET can extract text from a wide variety of file formats and media sources.

## Extracting text from images

- [Extracting text from an image](/ocr/net/recognition/image/)  
  Reading text from raster images in JPEG, PNG, single-page TIFF, BMP, and GIF formats.
- [Extracting text from multi-page TIFF](/ocr/net/recognition/tiff/)  
  Reading text from multi-page TIFF images.
- [Extracting text from pixel array](/ocr/net/recognition/pixel/)  
  Reading text from images, provided as byte array or an array of Aspose.Drawing.Color objects.
- [Fast recognition](/ocr/net/fast-recognition/)  
  Reading images in fastest recognition mode that consumes minimum possible resources.
- [Recognizing single line](/ocr/net/recognize-single-line/)  
  Reading text from images containing a single line of text.
- [Extracting text from receipts](/ocr/net/recognition/receipt/)  
  Digitizing scanned receipts without manual retyping.
- [Extracting text from ID cards](/ocr/net/recognition/id-card/)  
  Automatically read text from scanned or photographed ID cards.
- [Extracting text from passports](/ocr/net/recognition/passport/)  
  Digitize scans or photos of passports.
- [Extracting text from vehicle license plates](/ocr/net/recognition/car-plate/)  
  Reading vehicle license plates without manual retyping.
- [Extracting text from invoices](/ocr/net/recognition/invoice/)  
  Digitizing scanned invoices without manual retyping.

## Extracting text from documents

- [Extracting text from PDF document](/ocr/net/recognition/pdf/)  
  Reading text from a PDF document that consists of scanned images without searchable text.

## Extracting text from other file formats

- [Extracting text from DjVu file](/ocr/net/recognition/djvu/)  
  Reading text from multi-page DjVu files.

## Extracting text from alternative media

- [Batch recognition](/ocr/net/batch-recognition/)  
  Reading text from a list of raster images, folder, or ZIP archive.
- [Extracting text from URL](/ocr/net/recognition/url/)  
  Reading text from raster images hosted on web sites.

## Identifying recognition problems

Non-fatal recognition errors are stored as a list of strings in the `Warnings` property of the [recognition result](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/).

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png",recognitionSettings);
foreach(string warning in result.Warnings)
{
	Console.WriteLine(warning);
}
```
