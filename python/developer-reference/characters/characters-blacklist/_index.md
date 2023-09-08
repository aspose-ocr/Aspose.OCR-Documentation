---
weight: 30
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
url: /python-net/characters-blacklist/
feedback: OCRPYNET
title: Defining the blacklist of characters
description: How to ignore certain image defects that may be incorrectly recognized as characters.
keywords:
- blacklist
- symbols
- characters
- letters
- deny
---

Image defects such as dirt and scratches may cause recognition errors. For example, dots or other print defects next to letters can be incorrectly recognized as punctuation or diacritical marks.

To ignore certain characters during recognition, provide them in `ignored_symbols` property of recognition settings as a case-sensitive string:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Limit a subset of recognized characters
recognitionSettings = RecognitionSettings()
recognitionSettings.ignored_symbols = "Áá"
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
