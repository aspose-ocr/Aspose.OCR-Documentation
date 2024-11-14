---
weight: 50
date: "2024-11-13"
author: "Vladimir Lapin"
type: docs
url: /java/areas-detection/curved_text/
feedback: OCRJAVA
title:  DetectAreasMode.CURVED_TEXT
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.CURVED_TEXT algorithm.
keywords:
- structure
- region
- area
- photo
- distort
- curve
---

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/java/modules/) advanced OCR models (**aspose-ocr-advanced-recognition-v1**) in your project.
{{% /alert %}}

When photographing pages of books and magazine articles, the cylindrical curvature of the page results in distortion of the image, causing the lines of text to curl. This 3D geometric distortion negatively affects recognition.

**DetectAreasMode.CURVED_TEXT** areas detection mode uses a specialized neural network that automatically tracks and rectifies curved lines of text. This greatly improves recognition accuracy and allows much more text to be recovered and extracted.

![Detecting and rectifying curved lines of text](curved_text.png)

However, this algorithm is less efficient and consumes more resources when dealing with perfectly straight images, such as a single scanned sheet of paper. Try [**DetectAreasMode.MULTICOLUMN**](/ocr/java/areas-detection/multicolumn/) or [**DetectAreasMode.UNIVERSAL**](/ocr/java/areas-detection/universal/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.CURVED_TEXT);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.add("image.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(images, recognitionSettings);
System.out.println("Recognition result:\n" + results[0].recognitionText + "\n\n");
```
