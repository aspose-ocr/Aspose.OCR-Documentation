---
weight: 20
date: "2022-09-30"
author: "Vladimir Lapin"
type: docs
url: /java/image-regions-line-find/
feedback: OCRJAVA
aliases:
- /java/result-get-lines/
title: Finding line bounding boxes
description: Automatic detection of line bounding boxes inside an image.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
---

Aspose.OCR allows you to automatically find the coordinates of image regions containing text lines. This can be useful for highlighting detected lines when previewing an image or [extracting](/ocr/java/image-regions-extract/) individual blocks of text.

To get bounding boxes of all lines of the image, use `getTextAreas` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. Specify [`AreasType.LINES`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AreasType) as the **areaType** parameter of the method.

Line detection works differently depending on the `isDetectAreas` parameter of the method:

detectAreas | Behavior
----------- | --------
`true`      | The OCR engine tries to [break the content](/ocr/java/areas-detection/) into paragraphs and then extracts lines from the found paragraphs. Best suited for multi-column texts - adjacent lines in different columns will be treated as separate lines rather than a single line.
`false`     | The OCR engine ignores the columns and combines adjacent lines from different columns into a single line. This can be useful when concatenating text from table rows.

{{% alert color="primary" %}}
This method works for images in the following formats: GIF, PNG, JPEG, BMP, WBMP.
{{% /alert %}}

{{< tabs tabID="1" tabTotal="2" tabName1="From file" tabName2="From stream" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
ArrayList<Rectangle> paragraphs = api.getTextAreas("source.png", AreasType.LINES, true);
paragraphs.forEach((region) -> {
	System.out.println(region.recognitionText);
});
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
BufferedImage source = ImageIO.read(new File("source.png"));
ArrayList<Rectangle> paragraphs = api.getTextAreas(source, AreasType.LINES, true);
paragraphs.forEach((region) -> {
	System.out.println(region.recognitionText);
});
```
{{< /tab >}}
{{< /tabs >}}

Coordinates of each line (top-left corner, width and height) are returned as a list of [`Rectangle`](https://docs.oracle.com/javase/8/docs/api/java/awt/Rectangle.html) objects.
