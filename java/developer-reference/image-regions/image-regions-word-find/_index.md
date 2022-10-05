---
weight: 30
date: "2022-09-30"
author: "Vladimir Lapin"
type: docs
url: /java/image-regions-word-find/
aliases:
- /java/get-words-coordinates/
title: Finding word bounding boxes
description: Automatic detection of word bounding boxes inside an image.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
---

Aspose.OCR allows you to automatically find the coordinates of image rectangles containing individual words in text. This can be useful for highlighting detected words when previewing an image.

To get bounding boxes of all words of the image, use `getTextAreas` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. Specify [`AreasType.WORDS`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AreasType) as the **areaType** parameter of the method. `isDetectAreas` parameter of the method is ignored.

{{% alert color="primary" %}}
This method works for images in the following formats: GIF, PNG, JPEG, BMP, WBMP.
{{% /alert %}}

{{< tabs tabID="1" tabTotal="2" tabName1="From file" tabName2="From stream" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
ArrayList<Rectangle> paragraphs = api.getTextAreas("source.png", AreasType.WORDS);
paragraphs.forEach((region) -> {
	System.out.println(region.recognitionText);
});
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
BufferedImage source = ImageIO.read(new File("source.png"));
ArrayList<Rectangle> paragraphs = api.getTextAreas(source, AreasType.WORDS);
paragraphs.forEach((region) -> {
	System.out.println(region.recognitionText);
});
```
{{< /tab >}}
{{< /tabs >}}

Coordinates of each word (top-left corner, width and height) are returned as a list of [`Rectangle`](https://docs.oracle.com/javase/8/docs/api/java/awt/Rectangle.html) objects.
