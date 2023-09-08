---
weight: 10
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
url: /python-net/ocrinput/image-by-pixel/
feedback: OCRPYNET
title: Providing an image as pixel array
description: Adding an image as an array of pixels to the spose.OCR for Python via .NET recognition package.
keywords:
- image
- pixels
- bytes
- shade of gray
- brightness
---

Aspose.OCR for Python via .NET allows you to [provide](/ocr/python-net/ocrinput/#adding-source-content) an image for recognition as an array of pixels. This can be useful when working with [unsupported](/ocr/python-net/supported-file-formats/) file formats or with raw bitmap data.

Pixels are listed from left to right (by line), and each line is added to the array from top to bottom.

![Color ordering](pixel-order.png)

## Adding color image

The color image is added as a flat byte array representing the amount of each color per pixel. The amount ranges from 0 to 255, where 0 means no that color and 255 is the maximum amount of that color. For example, 2x2 pixels color bitmap is represented as the following byte array in RGB color model:

![RGB color array](pixel-order-rgb.png)

Because the pixel array does not contain an image header, you must directly specify the image's width and height, as well as its color model.

Color model | Bytes per pixel | Pixel color order
----------- | :-------------: | ------------------
`PixelType.RGB` | 3 | <ol><li>Red</li><li>Green</li><li>Blue</li></ol>
`PixelType.BGR` | 3 | <ol><li>Blue</li><li>Green</li><li>Red</li></ol>
`PixelType.RGBA` | 4 | <ol><li>Red</li><li>Green</li><li>Blue</li><li>Opacity</li></ol>

### Example

```python
input = OcrInput(InputType.SINGLE_IMAGE)
pixels = [pixel_1_red, pixel_1_green, pixel_1_blue, ..., pixel_n_red, pixel_n_green, pixel_n_blue]
input.add(bytearray(pixels), image_width, image_height, PixelType.RGB)
```

## Adding grayscale image

The image is provided as a flat byte array, where each byte represents the degree of pixel brightness (one byte per pixel). The number ranges from 0 to 255, where 0 means black and 255 means white.

![Grayscale color array](pixel-order-grayscale.png)

Because the pixel array does not contain an image header, you must directly specify the image's width and height, as well as the grayscale (`PixelType.BYTE`) color model.

### Example

```python
input = OcrInput(InputType.SINGLE_IMAGE)
pixels = [pixel_1, pixel_2, ..., pixel_n]
input.add(bytearray(pixels), image_width, image_height, PixelType.BYTE)
```
