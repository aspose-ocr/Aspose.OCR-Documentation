---
weight: 10
date: "2022-12-10"
author: "Vladimir Lapin"
type: docs
url: /cpp/fast-recognition/
title: Fast recognition
description: How to read text from high-quality scans using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Very simple and clear images, such as high-quality scans, do not require [automated corrections](/ocr/cpp/image-preprocessing/) and [areas detection](/ocr/cpp/areas-detection/).

Aspose.OCR can work in the fastest recognition mode that consumes minimum possible resources using the following methods:

Method | Description
------ | -----------
[`page_fast()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaca66b51299e489045665d03e51edc7f6) | Quickly read the image without automatic [text areas detection](/ocr/cpp/areas-detection/) and [skew angle correction](/ocr/cpp/deskew/#automatic-skew-correction).
[`page_fast_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaa9058576c6640eabbcd2cc9a418bad66) | Quickly read the image provided as an array of pixels without automatic [text areas detection](/ocr/cpp/areas-detection/) and [skew angle correction](/ocr/cpp/deskew/#automatic-skew-correction).


```cpp
std::string image_path = "../Data/Source/Source.img";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
aspose::ocr::page_fast(image_path.c_str(), buffer, len);
std::wcout << buffer;
```

## Performance impact

This method is about **twice as fast** as regular recognition and is recommended for public web applications and mobile devices.

## Drawbacks

This recognition mode does not work with skewed images and does not support [recognition settings](/ocr/cpp/settings/). However, you can [preprocess](/ocr/cpp/image-preprocessing/) an image before sending it to the OCR engine.
