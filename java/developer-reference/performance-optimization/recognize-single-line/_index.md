---
weight: 20
date: "2022-10-04"
author: "Vladimir Lapin"
type: docs
url: /java/recognize-single-line/
feedback: OCRJAVA
title: Recognize single line
description: How to read text from images containing a single line of text.
keywords:
- line
- simple
- fast
---

If an image contains a single line of text, it can be recognized in the fastest possible mode, without [automated corrections](/ocr/java/image-preprocessing/), [areas detection](/ocr/java/areas-detection/), and other resource-consuming steps.

To extract text from such images, use `RecognizeLine` method of of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class or use `setRecognizeSingleLine(true)` method of [recognition settings](/ocr/java/recognition-settings/).

{{< tabs tabID="1" tabTotal="3" tabName1="Recognize image from path" tabName2="Recognize image from memory" tabName3="Recognition settings" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
String result = RecognizeLine("source.png");
System.out.println("Recognition result:\n" + result + "\n\n");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
BufferedImage source = ImageIO.read(new File("source.png"));
String result = RecognizeLine(source);
System.out.println("Recognition result:\n" + result + "\n\n");
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```java
AsposeOCR api = new AsposeOCR();
// Activate single-line recognition mode
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setRecognizeSingleLine(true);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Show recognition result
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
{{< /tab >}}
{{< /tabs >}}

{{% alert color="primary" %}}
Please note that this method only works for images containing a single line of text! Using it on multi-line images will lead to incorrect recognition results.
{{% /alert %}}

## Performance impact

This method is about **7 times faster** than normal OCR and is highly recommended for batch processing large numbers of very simple images.

## Drawbacks

This recognition method only supports images in the following formats:

- GIF,
- 24-bit PNG,
- JPEG,
- BMP,
- WBMP.

It also does not work with skewed images and does not support [recognition settings](/ocr/java/recognition-settings/). However, you can [preprocess](/ocr/java/image-preprocessing/) an image before sending it to the OCR engine.
