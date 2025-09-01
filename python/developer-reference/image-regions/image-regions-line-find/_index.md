---
weight: 20
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/image-regions-line-find/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET can automatically find the coordinates of image regions containing text lines. This can be useful for highlighting detected areas when previewing an image.

To get bounding boxes of all lines in images, provided in [`OcrInput` object](/ocr/python-net/ocrinput/), use `detect_rectangles()` method. Specify `AreasType.LINES` as the **areas_type** parameter of the method.

Line detection works differently depending on the **detect_areas** parameter of the method:

detect_areas | Behavior
------------ | --------
`true`       | The OCR engine tries to [break the content](/ocr/python-net/areas-detection/) into paragraphs and then extracts lines from the found paragraphs. Best suited for multi-column texts - adjacent lines in different columns will be treated as separate lines rather than a single line.
`false`      | The OCR engine ignores the columns and combines adjacent lines from different columns into a single line. This can be useful when concatenating text from table rows.

The method returns a list of [`RectangleOutput`](https://reference.aspose.com/ocr/python-net/aspose.ocr/rectangleoutput/) objects containing coordinates of each line in each image.

{{% alert color="primary" %}}
PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `RectangleOutput` objects than the number of pages in the document.
{{% /alert %}}

Property | Description
-------- | -----------
`rectangles` | Coordinates of each line of an image (top-left corner, width and height), returned as a list of [`Rectangle`](https://reference.aspose.com/ocr/python-net/aspose.ocr/rectangle/) objects.
`image_index` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`page` | Page number. When working with single-page images, this value is always 0.
`source` | The full path or URL of the source file. If the file is provided as a stream, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect lines in multiple images:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Detect lines
results = api.detect_rectangles(input, AreasType.LINES, true)
for region in results[0].rectangles:
    print(region.top + ", " + region.left + ", " + region.width + ", " + region.height)
```
