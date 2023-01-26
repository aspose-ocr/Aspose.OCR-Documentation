---
weight: 30
date: "2022-11-08"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/tiff/
feedback: OCRJAVA
aliases:
- /java/recognize-tiff/
- /ocr/java/perform-ocr-operation-on-a-multipage-tiff-in-ruby/
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

To extract text from a multi-page TIFF image, use `RecognizeTiff` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-document/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) objects, corresponding to each recognized page.

{{< tabs tabID="1" tabTotal="2" tabName1="Read TIFF from path" tabName2="Read TIFF from memory" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
DocumentRecognitionSettings recognitionSettings = new DocumentRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from multi-page TIFF
ArrayList<RecognitionResult> results = api.RecognizeTiff("source.tiff", recognitionSettings);
results.forEach((page) -> {
	System.out.println(page.recognitionText);
});
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
DocumentRecognitionSettings recognitionSettings = new DocumentRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from multi-page TIFF
InputStream inputStream = new FileInputStream("source.tiff");
ArrayList<RecognitionResult> results = api.RecognizeTiff(inputStream, recognitionSettings);
results.forEach((page) -> {
	System.out.println(page.recognitionText);
});
```
{{< /tab >}}
{{< /tabs >}}
