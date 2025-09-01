---
weight: 35
date: "2024-07-01"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/areas-detection/universal/
feedback: OCRCPP
title:  detect_areas_mode_enum::UNIVERSAL
description: How Aspose.OCR determines the structure of a document using the detect_areas_mode_enum::UNIVERSAL algorithm.
keywords:
- structure
- region
- area
- blocks
- photo
- universal
---

On average, this algorithm achieves good results with most image types.

It is an optimal choice for general image processing, which can handle both simple scans and complex cases like posters, billboards, or random photos. However, specialized algorithms can provide faster or more accurate results for their intended use cases.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Fine-tune recognition
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::UNIVERSAL;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
