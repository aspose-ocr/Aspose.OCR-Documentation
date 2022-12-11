---
weight: 50
date: "2022-12-07"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognition/url/
aliases:
- /cpp/performing-ocr-on-an-image-from-url/
title: Extracting text from URL
description: How to read text from raster images in JPEG, PNG and BMP formats provided by web links.
keywords:
- read
- extract
- OCR
- recognize
- image
- picture
---

{{% alert color="primary" %}}
Reading an image provided with the web link is not supported in the Linux version of Aspose.OCR for C++.
{{% /alert %}}

Aspose.OCR for C++ can recognize images hosted on websites without downloading them to your computer. The only thing you need is the URL. Use [`page_from_uri()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga3081b88cf8506e06e33ffaade32f7352) method. This method supports JPEG, PNG and BMP images.

{{% alert color="primary" %}}
This method does not support authentication and can only work with public links.
{{% /alert %}}

This method allows you to optionally customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

```cpp
const char* uri = "https://upload.wikimedia.org/wikipedia/commons/e/e4/Biggle_horse_book_%28Page_45%29_BHL23865068.jpg";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
size_t res = aspose::ocr::page_from_uri(uri, buffer, len, settings);
std::wcout << buffer << L"\n";
```
