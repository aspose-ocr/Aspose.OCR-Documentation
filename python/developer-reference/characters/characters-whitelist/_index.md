---
weight: 20
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/characters-whitelist/
feedback: OCRPYNET
title: Defining the whitelist of characters
description: How to limit the set of characters Aspose.OCR for Python via .NET engine will look for.
keywords:
- whitelist
- symbols
- characters
- letters
- allow
---

Limiting a subset of characters instead of using the [full set](/ocr/python-net/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption. A list of characters can be automatically [identified](/ocr/python-net/characters-identify/) from an image using the built-in Aspose.OCR for Python via .NET mechanisms.

You can specify a list of characters Aspose.OCR for Python via .NET engine will look for in `allowed_symbols` property of recognition settings. The characters are provided as a _case-sensitive_ string.

Characters that do not match the provided list are ignored.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Limit a subset of recognized characters
recognitionSettings = RecognitionSettings()
recognitionSettings.allowed_symbols = "AÁBCDEÉFG12345"
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
