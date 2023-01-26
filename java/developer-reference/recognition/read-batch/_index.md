---
weight: 60
date: "2022-09-29"
author: "Vladimir Lapin"
type: docs
url: /java/batch-recognition/
feedback: OCRJAVA
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

Aspose.OCR for Java can read up to **20 images** in a single call. Images are be provided as a list of files, a folder, or a ZIP archive. Use `RecognizeMultiplePages` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. This method supports JPEG, PNG, BMP, GIF, and WBMP images.

{{% alert color="primary" %}}
Subfolders and nested archives are not supported.
{{% /alert %}}

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-image/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) objects, corresponding to each recognized page.

{{< tabs tabID="1" tabTotal="3" tabName1="Read multiple images" tabName2="Read images from ZIP achive" tabName3="Read images from folder" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
// Files list
ArrayList<String> images = new ArrayList<String>();
images.add("page1.png");
images.add("page2.png");
images.add("page3.png");
// Extract text from images
ArrayList<RecognitionResult> results = api.RecognizeMultiplePages(images, new RecognitionSettings());
// Save all pages as PDF
api.SaveMultipageDocument("result.pdf", Format.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
// Extract text from ZIP archive
ArrayList<RecognitionResult> results = api.RecognizeMultiplePages("images.zip", new RecognitionSettings());
// Save all pages as PDF
api.SaveMultipageDocument("result.pdf", Format.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```java
AsposeOCR api = new AsposeOCR();
// Extract text from ZIP archive
ArrayList<RecognitionResult> results = api.RecognizeMultiplePages("/images/", new RecognitionSettings());
// Save all pages as PDF
api.SaveMultipageDocument("result.pdf", Format.Pdf, results);
```
{{< /tab >}}
{{< /tabs >}}
