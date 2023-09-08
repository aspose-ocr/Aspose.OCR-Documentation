---
weight: 20
date: "2023-08-31"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognize-single-line/
feedback: OCRPYNET
title: Recognize single line
description: How to read text from images containing a single line of text.
keywords:
- line
- simple
- fast
---

If an image contains a single line of text, it can be recognized in the fastest possible mode, without [automated corrections](/ocr/python-net/image-processing/), [areas detection](/ocr/python-net/areas-detection/), and other resource-consuming steps. To extract text from such images, use `recognize_lines` method or enable `recognize_single_line` property in [recognition settings](/ocr/python-net/settings/).

This method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and optional [recognition settings](/ocr/python-net/recognition-settings-common/).

Recognition results are returned as a list of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) objects, that allow you to perform advanced manipulations with recognition results, including [automatic spelling correction](/ocr/python-net/spelling/) and [saving](/ocr/python-net/save/) results in various formats.

## Example

The following code example shows how to extract text from a single-line image:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")
input.add("source2.png")
# Recognize images
results = api.recognize_lines(input)
# Print recognition result
for result in results:
    print(result.recognition_text)
```

## Performance impact

This method is about **7 times faster** than normal OCR and is highly recommended for batch processing large numbers of very simple images.

## Drawbacks

This method only works for images which contain a single line of text! Using it on multi-line images will lead to incorrect recognition results.
