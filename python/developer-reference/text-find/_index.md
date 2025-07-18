---
weight: 110
date: "2023-08-31"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/find-text/
feedback: OCRPYNET
title: Finding text in an image
description: How to determine if an image contains provided text.
keywords:
- find
- detect
- identify
- locate
- text
- string
---

Aspose.OCR for Python via .NET makes searching for text in images as easy as finding the text fragment in a string. In a single line of code, you can search for a case-sensitive or case-insensitive string, and even validate an image text against a pattern.

To search for a text in an image, use `image_has_text()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class. The method either takes a text fragment or a regular expression and returns `true` if the text is found or `false` if not.

`image_has_text()` method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-common/).

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Configure recognition settings
recognitionSettings = RecognitionSettings()
recognitionSettings.auto_denoising = true
# Detect text
if api.image_has_text("source.png", "Aspose", recognitionSettings):
    print("The image contains the word \"Aspose\"")
else:
    print("The image doesn't contain the word \"Aspose\"")
```
