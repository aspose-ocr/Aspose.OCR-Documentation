---
weight: 40
date: "2023-09-01"
author: "Vladimir Lapin"
type: docs
url: /python-net/save-json/
feedback: OCRPYNET
title: Getting recognition results as JSON
description: Returning Aspose.OCR for Python via .NET recognition results in JSON format.
keywords:
- save
- result
- JSON
- output
---

Aspose.OCR for Python via .NET can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get the results as JSON, use `get_json()` method of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object.

Set `is_readable` parameter of the method to `true` to get a JSON string in a human-readable format with line breaks and auto-indentation.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
results = api.recognize(input)
# Show JSON
json = results[0].get_json(true)
print(json)
```
