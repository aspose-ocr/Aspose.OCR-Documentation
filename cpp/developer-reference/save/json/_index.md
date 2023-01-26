---
weight: 30
date: "2022-12-10"
author: "Vladimir Lapin"
type: docs
url: /cpp/save-json/
feedback: OCRCPP
aliases:
- /cpp/get-ocr-result-as-json/
title: Getting recognition results as JSON
description: Returning Aspose.OCR for C++ recognition results in JSON format.
keywords:
- save
- result
- JSON
- output
---

Aspose.OCR for C++ can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get the results as JSON, set `format` property of [recognition settings](/ocr/cpp/settings/) to `export_format::json` and call any [recognition method](/ocr/cpp/recognition/).

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.format = export_format::json;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
