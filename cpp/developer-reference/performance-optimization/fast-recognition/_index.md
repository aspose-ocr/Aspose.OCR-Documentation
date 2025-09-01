---
weight: 10
date: "2023-07-03"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/fast-recognition/
feedback: OCRCPP
title: Fast recognition
description: How to read text from high-quality scans using as few resources as possible.
keywords:
- recognize
- fast
- quick
---

Very simple and clear images, such as high-quality scans, do not require [automated corrections](/ocr/cpp/image-preprocessing/) and [areas detection](/ocr/cpp/areas-detection/).

Aspose.OCR for C++ can work in the fastest recognition mode that consumes minimum possible resources using `asposeocr_fast_recognize` function. This function takes one or more [`OcrInput`](/ocr/net/ocrinput/) objects and returns a list of recognition results, one result per image.

```cpp
// Provide the image
string file = current_dir + "/source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Extract text from the image
auto result = asposeocr_fast_recognize(content.data(), content.size());
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
```

## Performance impact

This function is about **twice as fast** as regular recognition and is recommended for public web applications and mobile devices.

## Drawbacks

This recognition mode does not work with skewed images and does not support [recognition settings](/ocr/cpp/settings/). However, you can [preprocess](/ocr/cpp/image-preprocessing/) an image before sending it to the OCR engine.
