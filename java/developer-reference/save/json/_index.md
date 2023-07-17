---
weight: 30
date: "2023-07-17"
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

Aspose.OCR for Java can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get the results as JSON, use `GetJson` method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/recognitionresult/) object.

```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save result
System.out.println(results[0].GetJson());
```
