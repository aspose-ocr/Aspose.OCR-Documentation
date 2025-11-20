---
weight: 59
date: "2025-11-27"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/formula-recognition/
aliases:
- /python-net/recognition/read-text-in-wild/
feedback: OCRPYNET
title: Formula recognition
description: Extracting and recognizing formulas from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- formula
- extract
- OCR
- recognize
---

Aspose.OCR for Python via .NET now provides a dedicated API for detecting and recognizing mathematical formulas in images, scanned documents, screenshots, or photos.
To extract formula text, simply call the universal [`aspose.ocr.AsposeOcr.recognize_formula`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) method.

This method accepts an `OcrInput` object and optional recognition settings.
Internally, formula detection uses the [`DetectAreasMode.FORMULA`](https://reference.aspose.com/ocr/python-net/aspose.ocr/detectareasmode/) mode to locate mathematical expressions before recognition.

Recognition results are returned as a list of `aspose.ocr.RecognitionResult` objects. Each result contains extracted formula text, detected regions, and allows exporting to various formats.


## DetectAreasMode.FORMULA

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")

# Set areas detection mode
recognitionSettings = RecognitionSettings()
recognitionSettings.detect_areas_mode = DetectAreasMode.FORMULA
# Recognize the image
results = api.recognize(input, recognitionSettings)

# Print recognition result
for result in results:
    print(result.recognition_text)
```

## RecognizeFormula(OcrInput images, bool detectAreas = true)

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")

# Recognize formulas with areas detection
results = api.recognize_formula(input, True)
# Parameter bool detectAreas - if set to true, automatically detects and isolates formula regions before performing recognition. If false, processes the entire image as a formula.

# Print recognition result
for result in results:
    print(result.recognition_text)
```
