---
weight: 40
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/resize/
feedback: OCRPYNET
title: Resizing 
description: How to scale or resize an image using Aspose.OCR for Python via .NET to improve recognition accuracy.
keywords:
- enlarge
- shrink
- width
- height
- upscale
- scale
---

The Aspose.OCR for Python via .NET recognition engine can handle images of any size. However, very small and very large image sizes can adversely affect recognition:

- _Small images_ may lose some detail due to noise removal, binarization, and automatic contrast correction.
- Recognizing _very large images_ can take much more time and resources.

Aspose.OCR for Python via .NET offers flexible processing filters that allow you to upscale small images, shrink large images, or resize an image to predefined width and height.

## Proportional image scaling

To scale images up or down proportionally, use the `scale` processing filter. The filter takes a scaling ratio (floating point number) as a parameter:

Scaling ratio | Result | Example
------------- | ------ | -------
`0` to `1`    | Shrink the image proportionally to the specified percentage. | `scale(0.3)` - proportionally reduce the width and height of the image down to 30%.
`1`           | Keep the original image size. | Do not apply scaling filter.
Above `1`     | Upscale the image proportionally to the specified percentage. | `scale(2)` - proportionally increase the width and height of the image to twice its original size.

Scaling filter also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/python-net/aspose.ocr.filters/interpolationfiltertype/) as an optional parameter.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.scale(2, InterpolationFilterType.TRIANGLE))
# Add image to the recognition batch and apply processing filter
input = OcrInput(InputType.SINGLE_IMAGE, filters)
input.add("source.png")
# Save processed image to the "result" folder
ImageProcessing.save(input, "result")
# Recognize the image
result = api.recognize(input)
# Print recognition result
print(result[0].recognition_text)
```

## Manual image resizing

You can manually define the width and height of the target image (in pixels) using the `resize` processing filter. It also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/python-net/aspose.ocr.filters/interpolationfiltertype/) as an optional parameter.

{{% alert color="primary" %}}
Applying this filter may cause the image to get out of proportion.
{{% /alert %}}

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.resize(1000, 1000, InterpolationFilterType.TRIANGLE))
# Add image to the recognition batch and apply processing filter
input = OcrInput(InputType.SINGLE_IMAGE, filters)
input.add("source.png")
# Save processed image to the "result" folder
ImageProcessing.save(input, "result")
# Recognize the image
result = api.recognize(input)
# Print recognition result
print(result[0].recognition_text)
```

## Usage scenarios 

- Medication guides.
- Food labels.
- Full-sized (raw) photos from high-resolution cameras and modern smartphones.
- Scanned images at very high (300+) DPI.
