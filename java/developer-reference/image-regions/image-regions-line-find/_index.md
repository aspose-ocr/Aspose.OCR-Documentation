---
weight: 20
date: "2023-07-17"
author: "Vladimir Lapin"
type: docs
url: /java/image-regions-line-find/
feedback: OCRJAVA
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

Aspose.OCR for Java can automatically find the coordinates of image regions containing text lines. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/java/image-regions-extract/) individual blocks of text.

To get bounding boxes of all lines in images, provided in [`OcrInput` object](/ocr/java/ocrinput/), use [`DetectRectangles`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/#DetectRectangles-com.aspose.ocr.OcrInput-com.aspose.ocr.AreasType-boolean-) method. Specify `AreasType.LINES` as the **areasType** parameter of the method.

Line detection works differently depending on the `isDetectAreas` parameter of the method:

isDetectAreas | Behavior
------------- | --------
`true`        | The OCR engine tries to [break the content](/ocr/java/areas-detection/) into paragraphs and then extracts lines from the found paragraphs. Best suited for multi-column texts - adjacent lines in different columns will be treated as separate lines rather than a single line.
`false`       | The OCR engine ignores the columns and combines adjacent lines from different columns into a single line. This can be useful when concatenating text from table rows.

The method returns a list of [`RectangleOutput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/rectangleoutput/) objects containing coordinates of each line in each image.

{{% alert color="primary" %}}
PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `RectangleOutput` objects than the number of pages in the document.
{{% /alert %}}

Property | Type | Description
-------- | ---- | -----------
`Rectangles` | `ArrayList<Rectangle>` | Coordinates of each line of an image (top-left corner, width and height), returned as a list of `Rectangle` objects.
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `String` | The full path or URL of the source file. If the file is provided as a `BufferedImage` object, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect lines in multiple images:

```java
AsposeOcr api = new AsposeOcr();
// Add images to detection batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.Add("source1.png");
images.Add("source2.jpg");
// Get line coordinates
ArrayList<RectangleOutput> areas = api.DetectRectangles(images, AreasType.LINES, true);
areas.forEach((area) -> {
	area.Rectangles.forEach((rectangle) -> {
		System.out.println("File: " + area.Source + " | " + rectangle.x + ", " + rectangle.y + ", " + rectangle.width + ", " + rectangle.height);
	});
});
```
