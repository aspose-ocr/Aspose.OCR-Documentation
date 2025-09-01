---
weight: 10
date: "2023-07-17"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/image-regions-paragraph-find/
feedback: OCRJAVA
title: Finding paragraph bounding boxes
description: Automatic detection of paragraph bounding boxes inside an image.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
---

Aspose.OCR for Java can automatically find the coordinates of image regions containing text paragraphs. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/java/image-regions-extract/) individual blocks of text.

To get bounding boxes of all paragraphs in images, provided in [`OcrInput` object](/ocr/java/ocrinput/), use [`DetectRectangles`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/#DetectRectangles-com.aspose.ocr.OcrInput-com.aspose.ocr.AreasType-boolean-) method. Specify `AreasType.PARAGRAPHS` as the **areasType** parameter of the method. `isDetectAreas` parameter of the method is ignored.

The method returns a list of [`RectangleOutput`](https://reference.aspose.com/ocr/java/com.aspose.ocr/rectangleoutput/) objects containing coordinates of each paragraph in each image.

{{% alert color="primary" %}}
PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `RectangleOutput` objects than the number of pages in the document.
{{% /alert %}}

Property | Type | Description
-------- | ---- | -----------
`Rectangles` | `ArrayList<Rectangle>` | Coordinates of each paragraph of an image (top-left corner, width and height), returned as a list of `Rectangle` objects.
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `String` | The full path or URL of the source file. If the file is provided as a `BufferedImage` object, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect paragraphs in multiple images:

```java
AsposeOcr api = new AsposeOcr();
// Add images to detection batch
OcrInput images = new OcrInput(InputType.SingleImage);
images.Add("source1.png");
images.Add("source2.jpg");
// Get paragraph coordinates
ArrayList<RectangleOutput> areas = api.DetectRectangles(images, AreasType.PARAGRAPHS);
areas.forEach((area) -> {
	area.Rectangles.forEach((rectangle) -> {
		System.out.println("File: " + area.Source + " | " + rectangle.x + ", " + rectangle.y + ", " + rectangle.width + ", " + rectangle.height);
	});
});
```
