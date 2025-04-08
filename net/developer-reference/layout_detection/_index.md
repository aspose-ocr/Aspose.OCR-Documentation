---
weight: 33
date: "2025-03-30"
author: "Vladimir Lapin"
type: docs
url: /net/layout_detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Layout detecton
description: How to detect the layout on the provided image.
keywords:
- layout
- locale
- detect
- find
---

Aspose.OCR for .NET can automatically analyze [image](https://docs.aspose.com/ocr/net/ocrinput/) content and identify the different types of layout blocks within it.

{{% alert color="primary" %}}
This functionality supports PNG, JPEG, BMP, TIFF, JFIF, and GIF images from files, streams, pixel arrays, and can bulk process folders and archives.
{{% /alert %}}

Pass one or more images as `Aspose.OCR.OcrInput` object to `Aspose.OCR.DetectDocumentLayout` method and get the layout blocks as `Aspose.OCR.LayoutOutput` object.

#### `Aspose.OCR.LayoutOutput`

This class stores a layout block detected in an image.

Property     | Type                           | Description
------------ | ------------------------------ | -----------
`Source`     | `string`                       | The full path to the file or URL, if applicable. Empty for images provided as a stream, byte array, or Base64.
`Page`       | `int`                          | Page number for multi-page images.
`Paragraphs` | `List<Aspose.OCR.ContentArea>` | Detected paragraphs.
`Images`     | `List<Aspose.OCR.ContentArea>` | Detected illustrations.
`Headers`    | `List<Aspose.OCR.ContentArea>` | Detected headers.
`Tables`     | `List<Aspose.OCR.ContentArea>` | Detected tables.
`Lists`      | `List<Aspose.OCR.ContentArea>` | Detected lists.
`Captions`   | `List<Aspose.OCR.ContentArea>` | Detected captions.
`Equations`  | `List<Aspose.OCR.ContentArea>` | Detected equations.

#### `Aspose.OCR.ContentArea`

This class stores a layout block detected in an image.

Property    | Type                   | Description
----------- | ---------------------- | -----------
`index`     | `int`                  | The sequential index of the content area, unique within the entire image.
`image`     | `MemoryStream`         | Image region (bitmap) with the content.
`Rectangle` | `Aspose.OCR.Rectangle` | The bounding rectangle of the content area.

## Example

The following code demonstrates how to find and recognize tables in an image

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Detect layout
Aspose.OCR.LayoutOutput layout = recognitionEngine.DetectDocumentLayout(input)[0];
List<Aspose.OCR.ContentArea> tables = layout.Tables
// Recognize tables
Aspose.OCR.OcrInput tableAreas = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
foreach(Aspose.OCR.ContentArea table in tables)
{
	tableAreas.Add(tables.image)
}
Aspose.OCR.OcrOutput recognResult = api.Recognize(tableAreas);
```
