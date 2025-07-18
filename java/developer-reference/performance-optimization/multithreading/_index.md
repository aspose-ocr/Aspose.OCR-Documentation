---
weight: 30
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/multithreading/
feedback: OCRJAVA
aliases:
- /java/multithreading-support-in-recognition/
title: Multithreading support
description: Optimize the resource usage by limiting the number of threads used by Aspose.OCR for Java recognition engine.
keywords:
- thread
- cpu
- core
---

Aspose.OCR for Java allows you to limit the number of threads used by the recognition engine. This may slow down the recognition speed, but will allow you to reserve some resources for other processes such as the parallel image processing, web server, database management system, or background data analysis.

To set the number of threads, use [`setThreadsCount`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setThreadsCount-int-) method of the [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class.

- If you specify `0` or do not set this parameter, the recognition engine will use all CPU cores.
- If you specify `1`, recognition will be performed on the application's main thread.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput images  = new OcrInput(InputType.SingleImage);
images.add("image1.png");
images.add("image2.png");
// Limit recognition load to 2 threads
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setThreadsCount(2);
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
results.forEach((result) -> {
	System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
});
```
