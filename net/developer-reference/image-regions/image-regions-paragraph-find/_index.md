---
weight: 10
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/image-regions-paragraph-find/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
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

Aspose.OCR for .NET can automatically find the coordinates of image regions containing text paragraphs. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/net/image-regions-extract/) individual blocks of text.

To get bounding boxes of all paragraphs in images, provided in [`OcrInput` object](/ocr/net/ocrinput/), use [`Aspose.OCR.AsposeOcr.DetectRectangles`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/detectrectangles/) method. Specify `Aspose.OCR.AreasType.PARAGRAPHS` as the **areasType** parameter of the method. `detectAreas` parameter of the method is ignored.

The method returns a list of [`Aspose.OCR.RectangleOutput`](https://reference.aspose.com/ocr/net/aspose.ocr/rectangleoutput/) objects containing coordinates of each paragraph in each image.

{{% alert color="primary" %}}
PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `Aspose.OCR.RectangleOutput` objects than the number of pages in the document.
{{% /alert %}}

Property | Type | Description
-------- | ---- | -----------
`Rectangles` | `List<Rectangle>` | Coordinates of each paragraph of an image (top-left corner, width and height), returned as a list of `Rectangle` objects.
`ImageIndex` | `int` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`Page` | `int` | Page number. When working with single-page images, this value is always 0.
`Source` | `string` | The full path or URL of the source file. If the file is provided as a `MemoryStream` object, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect paragraphs in multiple images:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Detect paragraphs
List<Aspose.OCR.RectangleOutput> results = recognitionEngine.DetectRectangles(input, Aspose.OCR.AreasType.PARAGRAPHS);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	foreach(Rectangle region in result.Rectangles) Console.WriteLine($"File: {result.Source} | {region.Top}, {region.Left}, {region.Width}, {region.Height}");
}
```
