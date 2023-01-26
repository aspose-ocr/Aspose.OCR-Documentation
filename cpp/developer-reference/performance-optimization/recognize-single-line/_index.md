---
weight: 20
date: "2022-12-10"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognize-single-line/
feedback: OCRCPP
title: Recognize single line
description: How to read text from images containing a single line of text.
keywords:
- line
- simple
- fast
---

If an image contains a single line of text, it can be recognized in the fastest possible mode, without [automated corrections](/ocr/cpp/image-preprocessing/), [areas detection](/ocr/cpp/areas-detection/), and other resource-consuming steps.

To extract text from such images, use the following methods:

Method | Description
------ | -----------
[`line()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga00aec23aeebdb45943cfc6db33539540) | Read a single-line image.
[`line_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga0776785aa5217a161e154bf499b3b824) | Read a single-line image provided as an array of pixels.
[`line_abc()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaf65e3c2c22843a71db64571b70ba1a12) | Read only the predefined list of characters from the single-line image.
[`line_abc_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga4b768b17e0ee76582153aeb11f4d2503) | Read only the predefined list of characters from the single-line image provided as an array of pixels.

```cpp
std::string image_path = "../Data/Source/Source.img";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
aspose::ocr::line(image_path.c_str(), buffer, len);
std::wcout << buffer;
```

{{% alert color="primary" %}}
Please note that this method only works for images containing a single line of text! Using it on multi-line images will lead to incorrect recognition results.
{{% /alert %}}

## Performance impact

This method is about **7 times faster** than normal OCR and is highly recommended for batch processing large numbers of very simple images.

## Drawbacks

This recognition method only supports images in the following formats:

- 24-bit PNG,
- JPEG,
- BMP.

It also does not work with skewed images and does not support [recognition settings](/ocr/cpp/settings/). However, you can [preprocess](/ocr/cpp/image-preprocessing/) an image before sending it to the OCR engine.
