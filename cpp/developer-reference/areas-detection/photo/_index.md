---
weight: 20
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/areas-detection/photo/
title:  detect_areas_mode_enum::PHOTO
description: How Aspose.OCR determines the structure of a document using the detect_areas_mode_enum::PHOTO algorithm.
keywords:
- structure
- region
- area
- blocks
- receipt
- screenshot
- photo
---

This algorithm works best with sparse irregular text and low-quality photos. It detects smaller text areas in an image, such as individual words, phrases, or lines, and then positions them relative to each other in recognition results.

![detect_areas_mode_enum::PHOTO algorithm](taa.png)

It is optimal for invoices, screenshots, driver's licenses, social security cards, government and work IDs, visas, math formulas, code snippets, and more. It can also detect small texts such as handwritten notes, signatures or stamps. In addition, it is well suited for reading smartphone photos and low-quality scans.

However, this algorithm may be less efficient when dealing with large amounts of structured textual data, such as articles and books, and does not support multi-column layout. Try [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::PHOTO;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
