---
weight: 10
date: "2023-08-31"
author: "Vladimir Lapin"
type: docs
url: /python-net/fast-recognition/
feedback: OCRPYNET
title: Fast recognition
description: How to read text from high-quality images using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Aspose.OCR for Python via .NET can work in the fastest recognition mode that consumes minimum possible resources using `recognize_fast()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns a list of strings, one string per image.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")
input.add("source2.png")
# Fast recognize images
results = api.recognize_fast(input)
# Print recognition result
for result in results:
    print(result)
```

## Performance impact

This method is about **twice as fast** as [regular recognition](/ocr/python-net/recognition/).

## Drawbacks

- This recognition method only works with high-quality scans without skew or distortion. However, you can [preprocess](/ocr/python-net/image-processing/#previewing-and-saving-processed-images) an image before sending it to the OCR engine.
- Fast recognition cannot be customized with [recognition settings](/ocr/python-net/settings/).
