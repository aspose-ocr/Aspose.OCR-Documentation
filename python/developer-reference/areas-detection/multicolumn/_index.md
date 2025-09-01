---
weight: 10
date: "2024-10-18"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/areas-detection/multicolumn/
aliases:
- /python-net/areas-detection/document/
feedback: OCRPYNET
title: DetectAreasMode.MULTICOLUMN
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.MULTICOLUMN algorithm.
keywords:
- structure
- region
- area
- blocks
- article
- colum
- document
---

This algorithm is optimized for handling large amounts of text arranged in multiple columns, such as scanned contracts, book pages, articles, and newspapers. Unlike other content detection methods that treat text as a single column, this approach processes each column individually.

![DetectAreasMode.MULTICOLUMN algorithm](dsr.png)

_\*The example article is Copyright &copy; 2016 CLINICS, distributed under the terms of the Creative Commons license._

However, it may not be suitable for analyzing photographs and small amounts of irregular text - try [**DetectAreasMode.UNIVERSAL**](/ocr/python-net/areas-detection/universal/) instead.

## Example

The following code sample demonstrates how to use this content areas detection algorithm:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Set document areas detection mode
recognitionSettings = RecognitionSettings()
recognitionSettings.detect_areas_mode = DetectAreasMode.MULTICOLUMN
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
