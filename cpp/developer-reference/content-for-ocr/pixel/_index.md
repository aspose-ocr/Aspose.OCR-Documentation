---
weight: 10
date: "2023-08-17"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/content-for-ocr/image-by-bytes/
aliases:
- /cpp/content-for-ocr/image-by-pixel/
feedback: OCRCPP
title: Providing an image as raw byte data
description: Providing an image as array of bytes or pixels to the Aspose.OCR for C++.
keywords:
- image
- pixels
- bytes
- raw
- shade of gray
- brightness
---

Aspose.OCR allows you to [provide](/ocr/cpp/content-for-ocr/) an image for recognition as raw data (bytes or pixels). This can be useful when creating in-memory OCR applications or working with [unsupported](/ocr/cpp/supported-file-formats/) file formats or with raw bitmaps.

## Providing image as pixel array

Pixels are listed from left to right (by line), and each line is added from top to bottom.

![Color ordering](pixel-order.png)

### Adding color image

The color image is provided in `raw_data` member of `AsposeOCRInput` structure as a string literal (`unsigned char*`), representing the amount of each color per pixel in red-green-blue (RGB) order. The amount ranges from 0 to 255, where 0 means no that color and 255 is the maximum amount of that color. For example, 2x2 pixels color bitmap is represented as following:

![RGB pixel data](pixel-order-rgb.png)

Because the raw pixel data does not contain an image header, you must directly specify:

`AsposeOCRInput` structure member | Type | Value
--------------------------------- | ---- | -----
`width` | `size_t` | Image width, in pixels.
`height` | `size_t` | Image height, in pixels.
`raw_data_size` | `size_t` | Raw pixel data size, equal to the number of pixels divided by 3.
`raw_data_type` | `AsposeOCRRawDataType` | Must be `AsposeOCRRawDataType.ASPOSE_OCR_RGB`.

### Adding grayscale image

The image is provided in `raw_data` member of `AsposeOCRInput` structure as a string literal (`unsigned char*`), where each byte represents the degree of pixel brightness (one byte per pixel). The value ranges from 0 to 255, where 0 means black and 255 means white.

![Grayscale pixel data](pixel-order-grayscale.png)

Because the raw pixel data does not contain an image header, you must directly specify:

`AsposeOCRInput` structure member | Type | Value
--------------------------------- | ---- | -----
`width` | `size_t` | Image width, in pixels.
`height` | `size_t` | Image height, in pixels.
`raw_data_size` | `size_t` | Raw pixel data size, equal to the number of pixels.
`raw_data_type` | `AsposeOCRRawDataType` | Must be `AsposeOCRRawDataType.ASPOSE_OCR_GRAYSCALE`.

## Providing image file as byte array

The image file (including a header) is provided as an array of bytes in `raw_data` member of `AsposeOCRInput` structure as a string literal (`unsigned char*`). Depending on the file format, you must directly specify:

`AsposeOCRInput` structure member | Type | Value
--------------------------------- | ---- | -----
`raw_data_size` | `size_t` | The size of the image byte array provided in `raw_data` member.
`raw_data_type` | `AsposeOCRRawDataType` | <ul><li>`ASPOSE_OCR_FORMAT_PNG` - PNG image;</li><li>`ASPOSE_OCR_FORMAT_JPG` - JPEG image.</li></ul>

## Providing ZIP archive as byte array

The ZIP archive file (including a header) is provided as an array of bytes in `raw_data` member of `AsposeOCRInput` structure as a string literal (`unsigned char*`). In addition to raw file data, you must directly specify:

`AsposeOCRInput` structure member | Type | Value
--------------------------------- | ---- | -----
`raw_data_size` | `size_t` | The size of the byte array containing ZIP archive provided in `raw_data` member.
`raw_data_type` | `AsposeOCRRawDataType` | Must be `ASPOSE_OCR_FORMAT_ZIP`.
