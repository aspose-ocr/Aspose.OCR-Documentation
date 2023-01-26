---
weight: 20
date: "2022-10-03"
author: "Vladimir Lapin"
type: docs
url: /java/save-text/
feedback: OCRJAVA
title: Getting recognition results as text
description: Returning Aspose.OCR for Java recognition results as formatted text.
keywords:
- save
- result
- text
- txt
- output
---

Recognition results in plain text with line breaks can be obtained from the `recognitionText` property of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) object or returned from `RecognizePage`, `RecognizePageFromUri`, `RecognizePageFast`, and `RecognizeLine` methods of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

{{< tabs tabID="1" tabTotal="2" tabName1="RecognitionText property" tabName2="RecognizePage method" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Get recognition results as plain text
String resultText = result.recognitionText;
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
String result = RecognizePage("source.png");
System.out.println("Recognition result:\n" + result + "\n\n");
```
{{< /tab >}}
{{< /tabs >}}

You can also extract text blocks from [specific image areas](/ocr/java/image-regions-extract/) or get [individual lines](/ocr/java/image-line-extract/).
