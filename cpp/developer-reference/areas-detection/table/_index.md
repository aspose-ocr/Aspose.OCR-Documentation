---
weight: 40
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/areas-detection/table/
feedback: OCRCPP
title:  detect_areas_mode_enum::TABLE
description: How Aspose.OCR determines the structure of a document using the detect_areas_mode_enum::TABLE algorithm.
keywords:
- structure
- region
- area
- table
- cell
- row
---

When this mode is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection mode is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::TABLE;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
