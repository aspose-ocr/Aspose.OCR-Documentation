---
weight: 10
date: "2023-08-26"
author: "Vladimir Lapin"
type: docs
url: /python-net/characters-identify/
feedback: OCRPYNET
title: Identifying the characters
description: Detecting the characters in an image.
keywords:
- symbols
- characters
- letters
- probability
- list
- detect
---

Aspose.OCR for Python via .NET can automatically build a list of characters found in an image and provide 4 less likely alternatives of each character (in descending order of probability). This list is provided in `recognition_characters_list` property of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
results = api.recognize(input)
# Get list of characters
characterList = results[0].recognition_characters_list
```

The list of _unique characters_ can later be used for identifying a [whitelist](/ocr/python-net/characters-whitelist/) to greatly improve the accuracy and performance of recognition.

_Alternatives_ can be used to find out patterns in common recognition errors, such as misidentifying certain characters in a font used in an image, and to take corrective action, such as automatic substitution.
