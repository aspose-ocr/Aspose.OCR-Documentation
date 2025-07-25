---
weight: 10
date: "2023-05-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/fast-recognition/
feedback: OCRJAVA
title: Fast recognition
description: How to read text from high-quality scans using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Aspose.OCR can work in the fastest recognition mode that consumes minimum possible resources using `RecognizeFast` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a list of strings, one string per image.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput images  = new OcrInput(InputType.SingleImage);
images.add(os.path.join(self.dataDir, "source1.png"));
images.add(os.path.join(self.dataDir, "source2.png"));
// Fast recognize images
ArrayList<RecognitionResult> results = api.RecognizeFast(images);
results.forEach((result) -> {
	System.out.println(result);
});
```

## Performance impact

This method is about **twice as fast** as [regular recognition](/ocr/java/recognition/).

## Drawbacks

- This recognition method only works with high-quality scans without skew or distortion. However, you can [preprocess](/ocr/java/image-preprocessing/) an image before sending it to the OCR engine.
- Fast recognition cannot be customized with [recognition settings](/ocr/java/settings/).
