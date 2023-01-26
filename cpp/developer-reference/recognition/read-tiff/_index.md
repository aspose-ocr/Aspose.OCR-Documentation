---
weight: 30
date: "2022-12-07"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognition/tiff/
feedback: OCRCPP
aliases:
- /cpp/recognize-multipage-tiff/
title: Extracting text from TIFF image
description: How to read text from single-page or multi-page TIFF images.
keywords:
- read
- extract
- OCR
- recognize
- TIF
- TIFF
- pages
- multiple
---

To extract text from a single-page or a multi-page TIFF image, use [`page_tiff()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga674b2d618113a5a244f4289acfd8f48e) method. You can also provide multiple TIFF images (individual pages) separated by semicolons.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

```cpp
std::string image_path = "source.tiff";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
size_t res_len = aspose::ocr::page_tiff("1.tif;2.tif", buffer, len, set);
std::wcout << buffer;
```
