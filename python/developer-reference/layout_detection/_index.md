---
weight: 32
date: "2025-03-03"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/layout_detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRPYNET
title: Layout detecton
description: How to detect the layout of the provided image.
keywords:
- layout
- areas
- detect
- find
---

{{% alert color="caution" %}} 
To use language detection, [install](/ocr/python-net/modules/) (**aspose-ocr-document-structure-detection-v1.ocr**) advanced OCR model to your project.
{{% /alert %}}

Aspose.OCR for .NET can automatically analyze [image](https://docs.aspose.com/ocr/python-net/ocrinput/) content and identify the different types of layout blocks within it.

Pass one or more images as `aspose.ocr.OcrInput` object to `aspose.ocr.detect_document_layout` method and get the layout blocks as `aspose.ocr.LayoutOutput` object.

The method accepts the collection of images in any of the [supported formats](/ocr/python-net/supported-file-formats/) and returns them as an array of `LayoutOutput` objects with the following properties:

#### `aspose.ocr.LayoutOutput`

This class stores a layout block detected in an image.

Property     | Type                           | Description
------------ | ------------------------------ | -----------
`source`     | `string`                       | The full path to the file or URL, if applicable. Empty for images provided as a stream, byte array, or Base64.
`page`       | `int`                          | Page number for multi-page images.
`paragraphs` | Array of `ContentArea`         | Detected paragraphs.
`images`     | Array of `ContentArea`         | Detected illustrations.
`headers`    | Array of `ContentArea`         | Detected headers.
`tables`     | Array of `ContentArea`         | Detected tables.
`lists`      | Array of `ContentArea`         | Detected lists.
`captions`   | Array of `ContentArea`         | Detected captions.
`equations`  | Array of `ContentArea`         | Detected equations.

#### `Aspose.OCR.ContentArea`

This class stores a layout block detected in an image.

Property    | Type                   | Description
----------- | ---------------------- | -----------
`index`     | `int`                  | The sequential index of the content area, unique within the entire image.
`rectangle` | `aspose.ocr.Rectangle` | The bounding rectangle of the content area.

## Example

The following code sample demonstrates how to detect the image layout:

```python
### Detect layout on the image

# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Detect layout
results = api.detect_document_layout(input)
# Print result
for result in results:
    print("paragraphs:" + str(len(result.paragraphs)))
    print("images:" + str(len(result.images)))
    print("tables:" + str(len(result.tables)))
    print("headers:" + str(len(result.headers)))
    print("lists:" + str(len(result.lists)))
    print("captions:" + str(len(result.captions)))
    print("equations:" + str(len(result.equations)))

# Recognize only headers
# Set rectangles for recognition
set = RecognitionSettings()
set.recognition_areas = [area.rectangle for area in result.headers] # use paragraphs or any other areas
# Recognize areas (rectangles)
results = api.recognize(input, set)
for result in results:
    print(result.recognition_text)

```
```
