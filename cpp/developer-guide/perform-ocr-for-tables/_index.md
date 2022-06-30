---
title: Perform OCR for tables
type: docs
weight: 61
url: /cpp/perform-ocr-for-tables/
---

Aspose.OCR for C++ supports identification and recognition of tabular structures. To enable automatic detection of table cells, set [`detect_areas_mode`](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#a23c6ab81de6f8ef6a4e7e84abc79cddd) recognition setting to `detect_areas_mode_enum::TABLE`.

## Example

Visit https://github.com/aspose-ocr/Aspose.OCR-for-C for the full project and sample data files.

```cpp
const string image = "table.jpg";

// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
const size_t len = 4096; 
wchar_t buffer[len] = { 0 };

// Activate automatic tables detection
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::TABLE;

// Read image
size_t size = asposeocr_page_settings(image.c_str(), buffer, len, settings);
#ifdef _WIN32
  setmode(_fileno(stdout), 0x00020000);
#else
  setlocale(LC_CTYPE, "");
#endif
  std::wcout << buffer;
```
