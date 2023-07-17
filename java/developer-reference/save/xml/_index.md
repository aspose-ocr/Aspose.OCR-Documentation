---
weight: 40
date: "2023-07-17"
author: "Vladimir Lapin"
type: docs
url: /java/save-xml/
feedback: OCRJAVA
title: Getting recognition results as XML
description: Returning Aspose.OCR for Java recognition results in XML format.
keywords:
- save
- result
- XML
- output
---

Aspose.OCR for Java can return recognition results as XML - a universal data exchange and storage format. To get the results as XML, use `GetXml` method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/recognitionresult/) object.

```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save result
System.out.println(results[0].GetXml());
```
