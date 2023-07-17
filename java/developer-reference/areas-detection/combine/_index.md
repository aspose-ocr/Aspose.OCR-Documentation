---
weight: 30
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
url: /java/areas-detection/combine/
feedback: OCRJAVA
title:  DetectAreasMode.COMBINE
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.COMBINE algorithm.
keywords:
- structure
- region
- area
- blocks
- photo
- universal
---

The combination of [**DetectAreasMode.DOCUMENT**](/ocr/java/areas-detection/document/) and [**DetectAreasMode.PHOTO**](/ocr/java/areas-detection/photo/), which can extract as much text from an image as possible. The OCR engine detects large blocks of text (such as paragraphs and columns), while the remaining content is analyzed by **DetectAreasMode.PHOTO** algorithm.

This allows you to handle even the most complex cases like posters, billboards, or random photos. However, it can take a little longer and may be less efficient than the specialized algorithms. Try one of the [dedicated area detection methods](/ocr/java/areas-detection/#area-detection-modes) if you are sure of the content type.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:


```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Enable automatic document areas detection
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.COMBINE);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.add("image.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
System.out.println("Recognition result:\n" + results[0].recognitionText + "\n\n");
```
