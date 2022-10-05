---
weight: 10
date: "2022-09-29"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/image/
aliases:
- /java/perform-ocr-on-an-image/
title: Extracting text from an image
description: How to read text from raster images in JPEG, PNG, TIFF, BMP, and GIF formats.
keywords:
- read
- extract
- OCR
- recognize
- image
- picture
---

To extract text from a raster image, use `RecognizePage` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. This method supports JPEG, PNG, BMP, GIF, and WBMP images.

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-image/).

Depending on the parameters, the method can either return a string with line breaks, or a [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) object that allows you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/java/spelling/), [get image regions](/ocr/java/image-regions-extract/) and [save](/ocr/java/save/) results in various formats.

{{< tabs tabID="1" tabTotal="3" tabName1="Read image from path" tabName2="Read image from memory" tabName3="Post-process recognition results" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
String result = RecognizePage("source.png");
System.out.println("Recognition result:\n" + result + "\n\n");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
BufferedImage source = ImageIO.read(new File("source.png"));
String result = RecognizePage(source);
System.out.println("Recognition result:\n" + result + "\n\n");
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Show non-critical recognition problems
result.warnings.forEach((w) -> {
	System.out.println(w);
});
// Get recognition results as JSON
String resultJson = result.GetJson();
```
{{< /tab >}}
{{< /tabs >}}
