---
weight: 70
date: "2025-01-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/recognition/
aliases:
- /python-net/recognition/read-text-in-wild/
feedback: OCRPYNET
title: Recognition
description: Extracting text from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- read
- extract
- OCR
- recognize
---

Reading text from any content in Aspose.OCR for Python via .NET is as easy as calling a universal `recognize()` method.

This method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and optional [recognition settings](/ocr/python-net/recognition-settings-common/).

Recognition results are returned as a `OcrOutput` object, that allow you to perform advanced manipulations with recognition results, including [automatic spelling correction](/ocr/python-net/spelling/) and [saving](/ocr/python-net/save/) results in various formats.

## Example

The following code example shows how to extract text from multiple images:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")
input.add("source2.png")
# Set recognition language
recognitionSettings = RecognitionSettings()
recognitionSettings.language = Language.UKR;
# Recognize the image
results = api.recognize(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```
