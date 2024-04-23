---
weight: 10
date: "2022-07-19"
author: "Vladimir Lapin"
type: docs
url: /cpp/areas-detection/document/
feedback: OCRCPP
title: detect_areas_mode_enum::DOCUMENT
description: How Aspose.OCR determines the structure of a document using the detect_areas_mode_enum::DOCUMENT algorithm.
keywords:
- structure
- region
- area
- blocks
- article
- colum
- document
---

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/cpp/modules/) **aspose-ocr-document-structure-detection-v1** recognition model in your project.
{{% /alert %}}

This algorithm works best with large amounts of structured text such as scanned contracts, book pages, articles, newspapers, and the like. It breaks content into larger blocks, such as paragraphs and columns. These blocks are then analyzed, read and combined into recognition results.

![detect_areas_mode_enum::DOCUMENT algorithm](dsr.png)

_\*The example article is Copyright &copy; 2016 CLINICS, distributed under the terms of the Creative Commons license._

However, it may not be suitable for analyzing photographs and small amounts of irregular text - try [**detect_areas_mode_enum::PHOTO**](/ocr/cpp/areas-detection/photo/) instead.

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
settings.detect_areas_mode = detect_areas_mode_enum::DOCUMENT;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
