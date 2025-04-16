---
weight: 33
date: "2025-04-15"
author: "Anna Pylaieva"
type: docs
url: /java/layout_detection/
feedback: OCRJAVA
title: Layout detecton
description: How to detect the layout on the provided image.
keywords:
- layout
- locale
- detect
- find
--- 

Aspose.OCR for Java can automatically analyze [image](https://docs.aspose.com/ocr/java/ocrinput/) content and identify the different types of layout blocks within it.

{{% alert color="primary" %}}
This functionality supports PDF, GIF, PNG, JPEG, BMP, or single-page TIFF from files, streams, and can bulk process folders and archives.
{{% /alert %}}

Pass one or more images as `com.aspose.ocr.OcrInput` object to `com.aspose.ocr.DetectDocumentLayout` method and get the layout blocks as `com.aspose.ocr.models.LayoutOutput` object.

#### `com.aspose.ocr.models.LayoutOutput`

This class stores a layout block detected in an image.

Property     | Type                                           | Description
------------ | ---------------------------------------------- | -----------
`source`     | `String`                                       | The full path to the file or URL, if applicable. Empty for images provided as a stream, byte array, or Base64.
`page`       | `Integer`                                      | Page number for multi-page images.
`paragraphs` | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected paragraphs.
`images`     | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected illustrations.
`headers`    | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected headers.
`tables`     | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected tables.
`lists`      | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected lists.
`captions`   | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected captions.
`equations`  | `ArrayList<com.aspose.ocr.models.ContentArea>` | Detected equations.

#### `com.aspose.ocr.models.ContentArea`

This class stores a layout block detected in an image.

Property    | Type                   | Description
----------- | ---------------------- | -----------
`index`     | `Integer`              | The sequential index of the content area, unique within the entire image.
`image`     | `BufferedImage`        | Image region with the content.
`rectangle` | `java.awt.Rectangle`   | The bounding rectangle of the content area.

## Example

The following code demonstrates how to find and recognize tables in an image

```java
AsposeOCR recognitionEngine = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(com.aspose.ocr.InputType.SingleImage);
input.add("source.png");
// Detect layout
com.aspose.ocr.models.LayoutOutput layout = recognitionEngine.DetectDocumentLayout(input).get(0);
ArrayList<com.aspose.ocr.models.ContentArea> tables = layout.tables;
// Recognize tables
com.aspose.ocr.OcrInput tableAreas = new OcrInput(com.aspose.ocr.InputType.SingleImage);
for(com.aspose.ocr.models.ContentArea table : tables)
{
    tableAreas.add(table.image);
}

com.aspose.ocr.OcrOutput recognResult = api.Recognize(tableAreas);
```
