---
weight: 141
date: "2025-06-15"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/debug/
feedback: OCRJAVA
title: Debug mode - Save processing results
description: How to enable debug mode and save preprocessed images and recognized text regions.
keywords:
- debug  
- visualization  
- intermediate result  
- text regions  
- preprocessing  
- save image  
---

Aspose.OCR for Java provides a **Debug Mode** that allows you to visually inspect how the input image is transformed during recognition.

When debug mode is enabled, the library saves intermediate processing results as image files:

- The **preprocessed image** after filters (e.g., binarization, noise removal, resizing).
- The **image with highlighted text regions**, where red rectangles mark detected text lines or blocks.

This feature is especially useful for troubleshooting recognition errors and fine-tuning preprocessing filters.

Property | Type | Description
-------- | ---- | -----------
`AsposeOCR.DebugMode` | `bool` | Enables or disables debug image saving.
`AsposeOCR.DebugModeSaveDirectory` | `String` | Sets the target folder where images will be saved. If not set, the current working directory is used.

## Enabling debug mode

Debug mode is activated using two static properties of the `AsposeOCR` class:


{{< tabs tabID="1" tabTotal="2" tabName1="Enable debug mode" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR.DebugMode = true;
AsposeOCR.DebugModeSaveDirectory = "C:/output/debug";
```
{{< /tab >}}
{{< /tabs >}}

## Output examples
When enabled, you will see image files like:
- Preprocessed0.png – image after applying preprocessing filters
- DetectedTextLines0.png – the same image with red rectangles drawn around detected text areas

Each image corresponds to the input from OcrInput.addImage(...) or its index.

**Notes**
- Debug images do not affect recognition accuracy.
- This feature works with both automatic and manual preprocessing.
- If a temporary license is used, debug mode still functions as expected.
