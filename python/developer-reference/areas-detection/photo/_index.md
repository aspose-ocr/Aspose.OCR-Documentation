---
weight: 20
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
url: /python-net/areas-detection/photo/
feedback: OCRPYNET
title: DetectAreasMode.PHOTO
description: How Aspose.OCR for Python via .NET determines the structure of a document using the DetectAreasMode.PHOTO algorithm.
keywords:
- structure
- region
- area
- blocks
- receipt
- screenshot
- photo
---

This algorithm works best with sparse irregular text and low-quality photos. It detects smaller text areas in an image, such as individual words, phrases, or lines, and then positions them relative to each other in recognition results.

![DetectAreasMode.PHOTO algorithm](taa.png)

It is optimal for invoices, screenshots, driver's licenses, social security cards, government and work IDs, visas, math formulas, code snippets, and more. It can also detect small texts such as handwritten notes, signatures or stamps. In addition, it is well suited for reading smartphone photos and low-quality scans.

However, this algorithm may be less efficient when dealing with large amounts of structured textual data, such as articles and books, and does not support multi-column layout. Try [**DetectAreasMode.DOCUMENT**](/ocr/python-net/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm in Aspose.OCR for Python via .NET:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Set document areas detection mode
recognitionSettings = RecognitionSettings()
recognitionSettings.detect_areas_mode = DetectAreasMode.PHOTO
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
