---
weight: 60
date: "2022-09-29"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/
title: Recognition
description: Extracting text from images, web links, and PDF documents.
keywords:
- read
- extract
- OCR
- recognize
---

Aspose.OCR for Java can extract text from a wide variety of file formats and media sources.

## Extracting text from images

- [Extracting text from an image](/ocr/java/recognition/image/)  
  Reading text from raster images in JPEG, PNG, WBMP, BMP, and GIF formats.
- [Extracting text from multi-page TIFF](/ocr/java/recognition/tiff/)  
  Reading text from multi-page TIFF images.
- [Extracting text from pixel array](/ocr/java/recognition/pixel/)  
  Reading text from images, provided as an array of pixels.
- [Fast recognition](/ocr/java/fast-recognition/)  
  Reading images in fastest recognition mode that consumes minimum possible resources.
- [Recognizing single line](/ocr/java/recognize-single-line/)  
  Reading text from images containing a single line of text.
- [Extracting text from receipts](/ocr/java/recognition/receipt/)  
  Digitizing scanned receipts without manual retyping.

## Extracting text from documents

- [Extracting text from PDF document](/ocr/java/recognition/pdf/)  
  Reading text from a PDF document that consists of scanned images without searchable text.

## Extracting text from alternative media

- [Batch recognition](/ocr/java/batch-recognition/)  
  Reading text from a list of raster images, folder, or ZIP archive.
- [Extracting text from URL](/ocr/java/recognition/url/)  
  Reading text from raster images hosted on web sites.

## Identifying recognition problems

Non-fatal recognition errors are stored as a list of strings in the `warnings` property of the [recognition result](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult).

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Show recognition errors
result.warnings.forEach((w) -> {
	System.out.println(w);
});
```
