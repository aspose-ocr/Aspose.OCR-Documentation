---
weight: 50
date: "2023-09-01"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/save-xml/
feedback: OCRPYNET
title: Getting recognition results as XML
description: Returning Aspose.OCR for Python via .NET recognition results in XML format.
keywords:
- save
- result
- XML
- output
---

Aspose.OCR for Python via .NET can return recognition results as XML - a universal data exchange and storage format. To get the results as XML, use `get_xml()` method of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
results = api.recognize(input)
# Show JSON
json = results[0].get_xml()
print(json)
```
