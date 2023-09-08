---
weight: 30
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
url: /python-net/areas-detection/combine/
feedback: OCRPYNET
title: DetectAreasMode.COMBINE
description: How Aspose.OCR for Python via .NET determines the structure of a document using the DetectAreasMode.COMBINE algorithm.
keywords:
- structure
- region
- area
- blocks
- photo
- universal
---

The combination of [**DetectAreasMode.DOCUMENT**](/ocr/python-net/areas-detection/document/) and [**DetectAreasMode.PHOTO**](/ocr/python-net/areas-detection/photo/), which can extract as much text from an image as possible. The Aspose.OCR for Python via .NET engine detects large blocks of text (such as paragraphs and columns), while the remaining content is analyzed by **DetectAreasMode.PHOTO** algorithm.

This allows you to handle even the most complex cases like posters, billboards, or random photos. However, it can take a little longer and may be less efficient than the specialized algorithms. Try one of the [dedicated area detection methods](/ocr/python-net/areas-detection/#area-detection-modes) if you are sure of the content type.

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
recognitionSettings.detect_areas_mode = DetectAreasMode.COMBINE
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
