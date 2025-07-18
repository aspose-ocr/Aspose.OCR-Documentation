---
weight: 40
date: "2024-03-01"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/areas-detection/table/
feedback: OCRPYNET
title:  DetectAreasMode.TABLE
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.TABLE algorithm.
keywords:
- structure
- region
- area
- table
- cell
- row
---

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/python-net/modules/) advanced OCR models (**aspose-ocr-advanced-recognition-v1**) in your project.
{{% /alert %}}

When this mode is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection mode is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**DetectAreasMode.DOCUMENT**](/ocr/python-net/areas-detection/document/) instead.

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
recognitionSettings.detect_areas_mode = DetectAreasMode.TABLE
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
