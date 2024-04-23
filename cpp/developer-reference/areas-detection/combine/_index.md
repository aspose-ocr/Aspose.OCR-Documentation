---
weight: 30
date: "2022-07-19"
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

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/cpp/modules/) **aspose-ocr-document-structure-detection-v1** recognition model in your project.
{{% /alert %}}

The combination of [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) and [**detect_areas_mode_enum::PHOTO**](/ocr/cpp/areas-detection/photo/), which can extract as much text from an image as possible. The OCR engine detects large blocks of text (such as paragraphs and columns), while the remaining content is analyzed by **detect_areas_mode_enum::PHOTO** algorithm.

This allows you to handle even the most complex cases like posters, billboards, or random photos. However, it can take a little longer and may be less efficient than the specialized algorithms. Try one of the [dedicated area detection functions](/ocr/cpp/areas-detection/#area-detection-modes) if you are sure of the content type.

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
settings.detect_areas_mode = detect_areas_mode_enum::COMBINE;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
