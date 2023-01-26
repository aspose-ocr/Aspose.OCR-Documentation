---
weight: 30
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/areas-detection/combine/
feedback: OCRCPP
title:  detect_areas_mode_enum::COMBINE
description: How Aspose.OCR determines the structure of a document using the detect_areas_mode_enum::COMBINE algorithm.
keywords:
- structure
- region
- area
- blocks
- photo
- universal
---

The combination of [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) and [**detect_areas_mode_enum::PHOTO**](/ocr/cpp/areas-detection/photo/), which can extract as much text from an image as possible. The OCR engine detects large blocks of text (such as paragraphs and columns), while the remaining content is analyzed by **detect_areas_mode_enum::PHOTO** algorithm.

This allows you to handle even the most complex cases like posters, billboards, or random photos. However, it can take a little longer and may be less efficient than the specialized algorithms. Try one of the [dedicated area detection methods](/ocr/cpp/areas-detection/#area-detection-modes) if you are sure of the content type.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::COMBINE;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
