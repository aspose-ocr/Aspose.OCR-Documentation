---
weight: 60
date: "2024-11-13"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/recognition/
aliases:
- /ocr/java/recognition/image/
- /ocr/java/recognition/pdf/
- /ocr/java/recognition/tiff/
- /ocr/java/recognition/url/
- /ocr/java/batch-recognition/
- /java/recognition/read-text-in-wild/
feedback: OCRJAVA
title: Recognition
description: Extracting text from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- read
- extract
- OCR
- recognize
---

Reading text from any content in Aspose.OCR for Java is as easy as calling a universal [`Recognize`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/#Recognize-com.aspose.ocr.OcrInput-com.aspose.ocr.RecognitionSettings-) method.

This method takes [`OcrInput` object](/ocr/java/ocrinput/) and optional [recognition settings](/ocr/java/recognition-settings-common/).

Recognition results are returned as a list of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/recognitionresult/) objects, that allow you to perform advanced manipulations with recognition results: [automatically correct spelling](/ocr/java/spelling/), [get image regions](/ocr/java/image-regions-extract/) and [save](/ocr/java/save/) results in various formats.

## Example

The following code example shows how to extract text from multiple images:

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput images  = new OcrInput(InputType.SingleImage);
images.add("image1.png");
images.add("image2.png");
// Recognition settings
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
