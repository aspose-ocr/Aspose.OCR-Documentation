---
weight: 10
date: "2022-08-31"
author: "Vladimir Lapin"
type: docs
url: /net/image-regions-paragraph-find/
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

Aspose.OCR allows you to automatically find the coordinates of image rectangles containing text paragraphs. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/net/image-regions-extract/) individual blocks of text.

To get bounding boxes of all paragraphs of the image, use [`GetRectangles`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/getrectangles/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. Specify `Aspose.OCR.AreasType.PARAGRAPHS` as the **areaType** parameter of the method. `detectAreas` parameter of the method is ignored.

{{% alert color="primary" %}}
This method works for images in the following formats: GIF, PNG, JPEG, BMP, TIFF.
{{% /alert %}}

{{< tabs tabID="1" tabTotal="2" tabName1="From file" tabName2="From stream" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
List<Aspose.Drawing.Rectangle> rectangleList = recognitionEngine.GetRectangles("source.png", Aspose.OCR.AreasType.PARAGRAPHS);
foreach(Aspose.Drawing.Rectangle rectangle in rectangleList)
{
	Console.WriteLine(rectangle.ToString());
}
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("source.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		List<Aspose.Drawing.Rectangle> rectangleList = recognitionEngine.GetRectangles(ms, Aspose.OCR.AreasType.PARAGRAPHS);
		foreach(Aspose.Drawing.Rectangle rectangle in rectangleList)
		{
			Console.WriteLine(rectangle.ToString());
		}
	}
}
```
{{< /tab >}}
{{< /tabs >}}

Coordinates of each paragraph (top-left corner, width and height) are returned as a list of [`Aspose.Drawing.Rectangle`](https://reference.aspose.com/pdf/net/aspose.pdf.drawing/rectangle/) objects.
