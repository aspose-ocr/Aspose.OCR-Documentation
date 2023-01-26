---
weight: 10
date: "2022-10-04"
author: "Vladimir Lapin"
type: docs
url: /java/fast-recognition/
feedback: OCRJAVA
title: Fast recognition
description: How to read text from high-quality scans using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Very simple and clear images, such as high-quality scans, do not require [automated corrections](/ocr/java/image-preprocessing/) and [areas detection](/ocr/java/areas-detection/).

Aspose.OCR can work in the fastest recognition mode that consumes minimum possible resources using [`RecognizePageFast`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePageFast-java.lang.String-) method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

```java
AsposeOCR api = new AsposeOCR();
String result = RecognizePageFast("source.png");
System.out.println("Recognition result:\n" + result + "\n\n");
```

## Performance impact

This method is about **twice as fast** as regular recognition and is recommended for public web applications and mobile devices.

## Drawbacks

This recognition mode does not work with skewed images and does not support [recognition settings](/ocr/java/recognition-settings/). However, you can [preprocess](/ocr/java/image-preprocessing/) an image before sending it to the OCR engine.
