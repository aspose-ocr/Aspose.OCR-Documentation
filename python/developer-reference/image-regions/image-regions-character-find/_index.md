---
weight: 40
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/image-regions-character-find/
feedback: OCRPYNET
title: Finding character bounding boxes
description: Character-by-character recognition and automatic detection of character bounding boxes inside images.
keywords:
- character
- symbol
- block
- rectangle
- area
- box
- boundary
- coordinates
---

Aspose.OCR for Python via .NET can perform character-by-character recognition and automatically detect bounding boxes of each recognized character using `recognize_characters()` method.

The method returns a list of [`CharacterRecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/characterrecognitionresult/) objects containing each recognized character along with its coordinates in each image.

Property | Description
-------- | -----------
`characters` | A list of recognized characters and their coordinates (top-left corner, width and height).
`image_index` | Sequence number of the image on the page. When working with single-page images, this value is always 0.
`page` | Page number. When working with single-page images, this value is always 0.
`source` | The full path or URL of the source file. If the file is provided as a stream, an array of pixels, or a Base64 string, this value will be empty.

## Example

The following code example shows how to detect characters in an image:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Detect words
results = api.recognize_characters(source, DetectAreasMode.COMBINE)
for c in results[0].characters:
    print("Found character " + c.Value + " by coordinates: left - " + c.Coordinates.X + " |  top - " + c.Coordinates.Y + " | width - " + c.Coordinates.Width + " | height - " + c.Coordinates.Height)
```
