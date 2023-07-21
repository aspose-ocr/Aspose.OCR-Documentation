---
weight: 30
date: "2023-07-20"
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

Aspose.OCR for C++ can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get recognition results in JSON format, call [`asposeocr_serialize_result()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga2ef1778bf26fdb773c29b988d3323160) function. You must provide the recognition result returned from [recognition function](/ocr/cpp/recognition/) in `recognition_result` parameter and `export_format::json` value in `format` parameter.

```cpp
// Provide images
string file = "page1.png";
AsposeOCRInput source1;
source1.url = file.c_str();
string file = "page2.png";
AsposeOCRInput source2;
source2.url = file.c_str();
std::vector<AsposeOCRInput> content = { source1, source2 };
// Fine-tune recognition
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::json);
std::cout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```

{{% alert color="primary" %}}
Do not forget to release the allocated memory by calling `asposeocr_free_result()` function.
{{% /alert %}}
