---
weight: 40
date: "2022-12-10"
author: "Vladimir Lapin"
type: docs
url: /cpp/save-xml/
title: Getting recognition results as XML
description: Returning Aspose.OCR for C++ recognition results in XML format.
keywords:
- save
- result
- XML
- output
---

Aspose.OCR for C++ can return recognition results as XML - a universal data exchange and storage format. To get the results as XML, set `format` property of [recognition settings](/ocr/cpp/settings/) to `export_format::xml` and call any [recognition method](/ocr/cpp/recognition/).

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.format = export_format::xml;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
