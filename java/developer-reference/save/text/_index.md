---
weight: 20
date: "2023-07-17"
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

Recognition results in plain text with line breaks can be obtained from the `recognitionText` property of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/recognitionresult/) object.

```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save result
System.out.println(results[0].recognitionText);
```

You can also extract text blocks from [specific image areas](/ocr/java/image-regions-extract/) or get [individual lines](/ocr/java/image-line-extract/).
