---
weight: 20
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/image-regions-line-find/
feedback: OCRNET
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

Aspose.OCR for .NET can automatically find the coordinates of image regions containing text lines. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/net/image-regions-extract/) individual blocks of text.

To get bounding boxes of all lines in images, provided in [`OcrInput` object](/ocr/net/ocrinput/), use [`Aspose.OCR.AsposeOcr.DetectRectangles`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/detectrectangles/) method. Specify `Aspose.OCR.AreasType.LINES` as the **areasType** parameter of the method.

Line detection works differently depending on the `detectAreas` parameter of the method:

detectAreas | Behavior
----------- | --------
`true`      | The OCR engine tries to [break the content](/ocr/net/areas-detection/) into paragraphs and then extracts lines from the found paragraphs. Best suited for multi-column texts - adjacent lines in different columns will be treated as separate lines rather than a single line.
`false`     | The OCR engine ignores the columns and combines adjacent lines from different columns into a single line. This can be useful when concatenating text from table rows.

The method returns a list of [`Aspose.OCR.RectangleOutput`](https://reference.aspose.com/ocr/net/aspose.ocr/rectangleoutput/) objects containing coordinates of each line in each image.

{{% alert color="primary" %}}
PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `Aspose.OCR.RectangleOutput` objects than the number of pages in the document.
{{% /alert %}}

Property | Type | Description
-------- | ---- | -----------
`Rectangles` | `List<Rectangle>` | Coordinates of each line of an image (top-left corner, width and height), returned as a list of `Rectangle` objects.
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `string` | The full path or URL of the source file. If the file is provided as a `MemoryStream` object, an array of pixels, or a Base64 string, this value will be empty.

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for .NET 23.3.1, this method replaces `GetRectangles` method.
{{% /alert %}}

## Example

The following code example shows how to detect lines in multiple images:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Detect lines
List<Aspose.OCR.RectangleOutput> results = recognitionEngine.DetectRectangles(input, Aspose.OCR.AreasType.LINES, true);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	foreach(Rectangle region in result.Rectangles) Console.WriteLine($"File: {result.Source} | {region.Top}, {region.Left}, {region.Width}, {region.Height}");
}
```
