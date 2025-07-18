---
weight: 30
date: "2023-09-01"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/save-text/
feedback: OCRPYNET
title: Getting recognition results as text
description: Returning Aspose.OCR for Python via .NET recognition results as formatted text.
keywords:
- save
- result
- text
- txt
- output
---

Recognition results in plain text with line breaks can be obtained from the `recognition_text` property of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
result = api.recognize(input)
# Print recognition result
print(result[0].recognition_text)
```
