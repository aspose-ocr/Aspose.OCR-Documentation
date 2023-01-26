---
weight: 20
date: "2022-12-10"
author: "Vladimir Lapin"
type: docs
url: /cpp/save-text/
feedback: OCRCPP
title: Getting recognition results as text
description: Returning Aspose.OCR for C++ recognition results as formatted text.
keywords:
- save
- result
- text
- txt
- output
---

Recognition results in plain text with line breaks are returned by default from any [recognition method](/ocr/cpp/recognition/), unless you directly specify another output format in [recognition settings](/ocr/cpp/settings/).

```cpp
std::string image_path = "source.png";
// prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
// extract text
size_t size = aspose::ocr::page(image_path.c_str(), buffer, len);
// print result
std::wcout << buffer << L"\n";
```

You can also extract text blocks from [specific image areas](/ocr/cpp/image-regions-extract/) or get [individual lines](/ocr/cpp/image-line-extract/).
