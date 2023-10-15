---
weight: 60
date: "2023-10-13"
author: "Vladimir Lapin"
type: docs
url: /python-net/areas-detection/text-in-wild/
feedback: OCRPYNET
title:  DetectAreasMode.TEXT_IN_WILD
description: How Aspose.OCR finds words on an image using the DetectAreasMode.TEXT_IN_WILD algorithm.
keywords:
- structure
- region
- area
- photo
- street
---

When this mode is enabled, Aspose.OCR engine finds individual words on images with sparse text. It is very effective when dealing with the following images:

- Street photos.
- Road signs.
- Signboards.
- Price tags.
- Food labels, nutritional information, ingredient lists.
- Menus.
- Catalogs.

This algorithm automatically activates detection of the coordinates of image regions containing [words](/ocr/python-net/image-regions-word-find/). There is no need to use `detect_rectangles()` method.

![Text-in-wild structure detection algorithm](label-regions.png)

However, this algorithm is very inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**DetectAreasMode.DOCUMENT**](/ocr/python-net/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Set document areas detection mode
recognitionSettings = RecognitionSettings()
recognitionSettings.detect_areas_mode = DetectAreasMode.TEXT_IN_WILD
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
```

## Limitations

The algorithm only works with Latin letters and numbers. You cannot specify the [recognition language](/ocr/python-net/languages/) and provide [whitelisted/blacklisted characters](/ocr/python-net/recognition-settings-common/). 
