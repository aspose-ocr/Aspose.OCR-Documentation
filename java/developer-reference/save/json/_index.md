---
weight: 30
date: "2022-10-03"
author: "Vladimir Lapin"
type: docs
url: /java/save-json/
feedback: OCRJAVA
aliases:
- /java/get-ocr-result-as-json/
title: Getting recognition results as JSON
description: Returning Aspose.OCR for Java recognition results in JSON format.
keywords:
- save
- result
- JSON
- output
---

Aspose.OCR for Java can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get the results as JSON, use [`GetJson`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#GetJson--) method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) object.

```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Get recognition results as JSON
String resultJSON = result.GetJson();
```
