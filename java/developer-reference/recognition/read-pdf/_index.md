---
weight: 20
date: "2022-09-29"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/pdf/
aliases:
- /java/recognize-scanned-pdf/
title: Extracting text from PDF document
description: How to read text from a scanned PDF and convert scanned documents into searchable PDF files.
keywords:
- read
- extract
- OCR
- recognize
- PDF
- scan
- document
---

To extract text from a PDF document that consists of scanned images without searchable text, use `RecognizePdf` method of [`AsposeOCRPdf`](https://reference.aspose.com/ocr/java/com.aspose.ocr.pdf/AsposeOCRPdf) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-document/).

The method returns a list of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) objects, corresponding to each recognized page.

{{< tabs tabID="1" tabTotal="2" tabName1="Read PDF from path" tabName2="Read PDF from memory" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCRPdf api = new AsposeOCRPdf();
// Customize recognition
DocumentRecognitionSettings recognitionSettings = new DocumentRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from PDF document
ArrayList<RecognitionResult> results = api.RecognizePdf("source.pdf", recognitionSettings);
results.forEach((page) -> {
	System.out.println(page.recognitionText);
});
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCRPdf api = new AsposeOCRPdf();
// Customize recognition
DocumentRecognitionSettings recognitionSettings = new DocumentRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from PDF document
InputStream inputStream = new FileInputStream("source.pdf");
ArrayList<RecognitionResult> results = api.RecognizePdf(inputStream, recognitionSettings);
results.forEach((page) -> {
	System.out.println(page.recognitionText);
});
```
{{< /tab >}}
{{< /tabs >}}
