---
weight: 30
date: "2023-08-17"
author: "Vladimir Lapin"
type: docs
url: /cpp/multithreading/
feedback: OCRCPP
title: Multithreading support
description: Optimize the resource usage and increase performance by setting the number of threads used by Aspose.OCR for C++ recognition engine.
keywords:
- thread
- cpu
- core
---

Aspose.OCR for C++ allows you to specify the number of threads used by the recognition engine. With it, you can balance performance and reserve some resources for other parallel processes such as image processing, background data analysis, and the like.

To set the number of threads (CPU cores) used by the OCR engine, use `asposeocr_set_allowed_thread_number()` function. By default, recognition is be performed on the application's main thread.

```cpp
// Use 8 threads for OCR
asposeocr_set_allowed_thread_number(8);
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
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```

To get the number of threads used by the recognition engine, use `asposeocr_get_allowed_thread_number()` function.
