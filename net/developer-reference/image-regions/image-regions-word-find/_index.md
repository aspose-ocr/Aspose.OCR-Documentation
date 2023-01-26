---
weight: 30
date: "2022-08-31"
author: "Vladimir Lapin"
type: docs
url: /net/image-regions-word-find/
feedback: OCRNET
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

To get bounding boxes of all words of the image, use [`GetRectangles`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/getrectangles/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. Specify `Aspose.OCR.AreasType.WORDS` as the **areaType** parameter of the method. `detectAreas` parameter of the method is ignored.

{{% alert color="primary" %}}
This method works for images in the following formats: GIF, PNG, JPEG, BMP, TIFF.
{{% /alert %}}

{{< tabs tabID="1" tabTotal="2" tabName1="From file" tabName2="From stream" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
List<Aspose.Drawing.Rectangle> rectangleList = recognitionEngine.GetRectangles("source.png", Aspose.OCR.AreasType.WORDS);
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
		List<Aspose.Drawing.Rectangle> rectangleList = recognitionEngine.GetRectangles(ms, Aspose.OCR.AreasType.WORDS);
		foreach(Aspose.Drawing.Rectangle rectangle in rectangleList)
		{
			Console.WriteLine(rectangle.ToString());
		}
	}
}
```
{{< /tab >}}
{{< /tabs >}}

Coordinates of each word (top-left corner, width and height) are returned as a list of [`Aspose.Drawing.Rectangle`](https://reference.aspose.com/pdf/net/aspose.pdf.drawing/rectangle/) objects.
