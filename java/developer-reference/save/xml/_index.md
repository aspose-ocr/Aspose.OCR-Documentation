---
weight: 40
date: "2022-10-03"
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

Aspose.OCR for Java can return recognition results as XML - a universal data exchange and storage format. To get the results as JSON, use [`GetXml`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#GetXml--) method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) object.

```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Get recognition results as JSON
String resultXML = result.GetXml();
```
