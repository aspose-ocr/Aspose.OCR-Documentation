---
weight: 10
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognition/image/
aliases:
- /cpp/perform-ocr-on-an-image/
title: Extracting text from an image
description: How to read text from raster images in JPEG, PNG, and BMP formats.
keywords:
- read
- extract
- OCR
- recognize
- image
- picture
---

To extract text from JPEG, PNG and BMP images, use one of the following methods:

Method | Description
------ | -----------
[`page()`](https://reference.aspose.com/ocr/cpp/groupAspose#gae4fb9b76d4b358a98b33909cc274ff82) | Read the image with automatic [text areas detection](/ocr/cpp/areas-detection/) and [skew angle correction](/ocr/cpp/deskew/#automatic-skew-correction).
[`page_settings()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga028cce64d935cf8fc8d5eab3d3713ebf) | Fine-tune [recognition settings](/ocr/cpp/settings/) and read the image.
[`page_all()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga4aea2d0695beb19955a23719eadf55d2) | Read the entire image without [text areas detection](/ocr/cpp/areas-detection/).
[`page_abc()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga0e6cc74793adbf5efdf4028d7f9161f9) | Read only the predefined list of characters from the images.
[`page_abc_all()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga5e96a883c6923558a138e229cf955be9) | Read only the predefined list of characters from the image without [text areas detection](/ocr/cpp/areas-detection/).

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
settings.auto_contrast = true;
settings.upscale_small_font = true;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
