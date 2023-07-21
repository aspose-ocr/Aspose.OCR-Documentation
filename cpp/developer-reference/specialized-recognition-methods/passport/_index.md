---
weight: 10
date: "2023-04-28"
author: "Vladimir Lapin"
type: docs
url: /cpp/passport-recognition/
feedback: OCRCPP
title: Extracting text from passport images
description: How to digitize scanned or photographed passports by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- passport
---

Automatic passport recognition and verification is a very common task in many areas: border control, banking, security, and so on. However, manually re-typing text is an error-prone and time-consuming process, and mistakes can lead to security breaches and other undesirable consequences.

Aspose.OCR offers a special recognition algorithm that extracts text from scanned or photographed passports, which can then be automatically saved to the database or automatically verified.

To extract text from a passport image, use `asposeocr_recognize_passport()` function. This function also allows you to customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

```cpp
// Provide the passport image
string file = current_dir + "/john_doe.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set recognition language
RecognitionSettings settings;
settings.language_alphabet = language::eng;
// Extract text from the image
auto result = asposeocr_recognize_passport(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::cout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
