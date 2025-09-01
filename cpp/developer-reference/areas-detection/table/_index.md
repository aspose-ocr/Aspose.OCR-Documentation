---
weight: 40
date: "2022-07-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
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

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/cpp/modules/) **aspose-ocr-advanced-recognition-v1** sparse recognition model in your project.
{{% /alert %}}

When this mode is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection mode is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) instead.

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
settings.detect_areas_mode = detect_areas_mode_enum::TABLE;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
