---
weight: 50
date: "2022-09-29"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/url/
feedback: OCRJAVA
aliases:
- /java/performing-ocr-on-an-image-from-url/
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

Aspose.OCR for Java can recognize images hosted on websites without downloading them to your computer. The only thing you need is the URL. Use `RecognizePageFromUri` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. This method supports JPEG, PNG, BMP, GIF, and single-page TIFF images.

{{% alert color="primary" %}}
This method does not support authentication and can only work with public links.
{{% /alert %}}

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-image/).

Depending on the parameters, the method can either return a string with line breaks, or a [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) object that allows you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/java/spelling/), [get image regions](/ocr/java/image-regions-extract/) and [save](/ocr/java/save/) results in various formats.

```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from image provided as URL
RecognitionResult result = api.RecognizePageFromUri("https://upload.wikimedia.org/wikipedia/commons/e/e4/Biggle_horse_book_%28Page_45%29_BHL23865068.jpg", recognitionSettings);
System.out.println("Recognition result:\n" + result + "\n\n");
```
