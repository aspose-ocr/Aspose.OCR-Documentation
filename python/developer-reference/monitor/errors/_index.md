---
weight: 10
date: "2023-09-02"
author: "Vladimir Lapin"
type: docs
url: /python-net/identify-problems/
feedback: OCRPYNET
title: Identifying recognition problems
description: How to identify non-fatal errors that occurred during recognition.
keywords:
- error
- issue
- problem
- catch
---

Non-fatal recognition errors are stored as a list of strings in the `warnings` property of the [recognition result](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/).

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
result = api.recognize(input)
# Output warnings
warnings = result[0].warnings
for warning in warnings:
    print(warning)
```
