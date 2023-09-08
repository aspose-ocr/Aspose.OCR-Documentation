---
weight: 100
date: "2023-08-31"
author: "Vladimir Lapin"
type: docs
url: /python-net/image-text-compare/
feedback: OCRPYNET
title: Comparing text in images
description: How to compare texts on two images.
keywords:
- compare
- similar
- difference
- diff
- text
---

Aspose.OCR for Python via .NET can compare texts on two images, regardless of the font, text size, case, styles, and colors.

To compare texts in 2 images, use `image_text_diff()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class. This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-common/).

`image_text_diff()` returns a number representing how similar the compared images are. The return value is a floating point number from 0 to 1; the lower the number, the more different image texts are. **0** means that the texts are completely different; **1** means the texts are identical. Fonts and styles are ignored.

{{% alert color="primary" %}}
The difference between image texts is calculated as the [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance). Simply put, it is the minimum number of changes required to transform one string into another by inserting, deleting or replacing a single character.
{{% /alert %}}

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Configure recognition settings
recognitionSettings = RecognitionSettings()
recognitionSettings.auto_denoising = true
# Case-insensitive comparison of image texts
if api.compare_image_texts("image1.png", "image2.png", recognitionSettings, true):
    # Percentage of similarity between texts
    distance = api.image_text_diff("image1.png", "image2.png", recognitionSettings, true)
    print("The image texts are {:.2%} similar".format(distance))
else:
    print("Images contain the same text")
```
