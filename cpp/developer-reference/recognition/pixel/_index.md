---
weight: 70
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognition/pixel/
title: Extracting text from pixel array
description: Extracting text from an image, provided as an array of pixels.
keywords:
- read
- extract
- OCR
- recognize
- pixel
- color
- byte
- array
---

Aspose.OCR allows you to provide an image for recognition as an array of pixels. This can be useful when working with [unsupported](/ocr/cpp/supported-file-formats/) image formats.

The image is provided as an [`ImageDescriptor` structure](https://reference.aspose.com/ocr/cpp/struct/image_descriptor/) which describes image width, height, a number of bytes per pixel, and pixel colors. Pixels are listed from left to right (by line), and each line is added to the array from top to bottom.

![Color ordering](pixel-order.png)

## Recognizing color images

The pixels are provided as a flat byte array representing the amount of each color (red, green and blue) per pixel. The amount can range from 0 to 255, where 0 means no that color and 255 is the maximum amount of that color. Set the `channels_size` member of [`ImageDescriptor` structure](https://reference.aspose.com/ocr/cpp/struct/image_descriptor/) to **3**.

## Recognizing grayscale images

The pixels are provided as a flat byte array representing the degree of pixel saturation (one byte per pixel). The number can range from 0 to 255, where 0 means black and 255 means white. Set the `channels_size` member of [`ImageDescriptor` structure](https://reference.aspose.com/ocr/cpp/struct/image_descriptor/) to **1**.

## Recognition methods

To extract text from an image provided as a pixel array, use one of the following methods:

Method | Description
------ | -----------
[`page_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga1afd83b426422cb9d1fa97f0e9065cdf) | Read the array with image pixels with automatic [text areas detection](/ocr/cpp/areas-detection/) and [skew angle correction](/ocr/cpp/deskew/#automatic-skew-correction).
[`page_settings_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga1872a2f84742f42bb774c4ddcbadf79d) | Fine-tune [recognition settings](/ocr/cpp/settings/) and read the byte array with image pixels.
[`page_all_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaf7260eceb89981ae54f138070ce22a6e) | Read the array with image pixels without [text areas detection](/ocr/cpp/areas-detection/).
[`page_abc_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaee6090566975888065f5896b012775ff) | Read only predefined list of characters from the array with image pixels.
[`page_abc_all_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga32105a78cbec618e939173e0cf10aec6) | Read only predefined list of characters from the array with image pixels without [text areas detection](/ocr/cpp/areas-detection/).

```cpp
unsigned char*** img_raw = <...>;
ImageDescriptor descriptor;
descriptor.image_from_raw_bytes = img_raw;
descriptor.height = 2000;
descriptor.width = 800;
descriptor.channels_size = 3;
const size_t descriptor_size = sizeof descriptor;
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
size_t res_len = aspose::ocr::page_from_raw_bytes(descriptor, descriptor_size, buffer, len);
std::wcout << buffer;
```
