---
weight: 30
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/image-regions-word-find/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET can automatically find the coordinates of image regions containing words. This can be useful for highlighting detected areas when previewing an image.

To get bounding boxes of all words in images, provided in [`OcrInput` object](/ocr/python-net/ocrinput/), use `detect_rectangles()` method. Specify `AreasType.WORDS` as the **areas_type** parameter of the method. **detect_areas** parameter of the method is ignored.

The method returns a list of [`RectangleOutput`](https://reference.aspose.com/ocr/python-net/aspose.ocr/rectangleoutput/) objects containing coordinates of each word in each image.

{{% alert color="primary" %}}
PDF documents can contain more than one image per page. Therefore, the resulting list can contain more `RectangleOutput` objects than the number of pages in the document.
{{% /alert %}}

Property | Description
-------- | -----------
`rectangles` | Coordinates of each word of an image (top-left corner, width and height), returned as a list of [`Rectangle`](https://reference.aspose.com/ocr/python-net/aspose.ocr/rectangle/) objects.
`image_index` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`page` | Page number. When working with single-page images, this value is always 0.
`source` | The full path or URL of the source file. If the file is provided as a stream, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect words in multiple images:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Detect words
results = api.detect_rectangles(input, AreasType.WORDS)
for region in results[0].rectangles:
    print(region.top + ", " + region.left + ", " + region.width + ", " + region.height)
```
