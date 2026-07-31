---
weight: 52
date: "2026-07-31"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/font-detection/
feedback: OCRPYNET
title: Font detection
description: How to detect font family, style, size, and confidence for recognized text lines.
keywords:
- font
- style
- size
- detect
- text line
---

Aspose.OCR for Python via .NET can detect font information for each recognized text line. This is useful when you need to preserve visual characteristics of recognized content or analyze documents by typography.

Font detection is enabled through `RecognitionSettings.detect_fonts`. When the setting is enabled, each non-empty item in `RecognitionResult.recognition_lines_result` can contain a `FontLineResult` object in its `font` property.

{{% alert color="primary" %}}
Font detection is designed for recognized text lines. Enable line-level recognition output and use clear, sufficiently large text images for best results.
{{% /alert %}}

## Font information

`FontLineResult` contains the following information:

Property | Description
-------- | -----------
`line_index` | Zero-based line index in the processed font batch.
`size_px` | Detected line height in pixels.
`size_pt_estimate` | Estimated font size in points.
`style` | Detected font style, for example `regular`, `italic`, or `bold_italic`.
`style_confidence` | Confidence score for the detected style.
`font` | Detected font family name.
`font_confidence` | Confidence score for the detected font family.

## Detecting fonts

Set `RecognitionSettings.detect_fonts` to `True`, recognize the image, and read the `font` property of each recognized line.

```python
import aspose.ocr

api = aspose.ocr.AsposeOcr()

input_data = aspose.ocr.OcrInput(aspose.ocr.InputType.SINGLE_IMAGE)
input_data.add("source.png")

settings = aspose.ocr.RecognitionSettings()
settings.detect_fonts = True
settings.detect_areas_mode = aspose.ocr.DetectAreasMode.LEAN
settings.language = aspose.ocr.Language.LATIN
settings.threads_count = 1

result = api.recognize(input_data, settings)[0]

for line in result.recognition_lines_result:
    if not line.text_in_line or not line.text_in_line.strip():
        continue

    font = line.font

    print(line.text_in_line)
    print(f"Font: {font.font} ({font.font_confidence:.0%})")
    print(f"Style: {font.style} ({font.style_confidence:.0%})")
    print(f"Size: {font.size_px}px / {font.size_pt_estimate}pt")
```

## Processing multiple images

Font detection works with batches. Each recognition result contains line-level font data for the corresponding input image or page.

```python
import aspose.ocr

api = aspose.ocr.AsposeOcr()

input_data = aspose.ocr.OcrInput(aspose.ocr.InputType.SINGLE_IMAGE)
input_data.add("arial.png")
input_data.add("calibri.png")

settings = aspose.ocr.RecognitionSettings()
settings.detect_fonts = True
settings.detect_areas_mode = aspose.ocr.DetectAreasMode.LEAN
settings.language = aspose.ocr.Language.LATIN
settings.threads_count = 1

for result in api.recognize(input_data, settings):
    for line in result.recognition_lines_result:
        if not line.text_in_line or not line.text_in_line.strip():
            continue
        print(f"{line.text_in_line}: {line.font.font}, {line.font.style}")
```
