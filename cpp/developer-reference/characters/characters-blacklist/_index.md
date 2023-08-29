---
weight: 30
date: "2023-07-18"
author: "Vladimir Lapin"
type: docs
url: /cpp/characters-blacklist/
feedback: OCRCPP
aliases:
- /cpp/provide-ignored-characters-during-ocr-operation/
title: Defining the blacklist of characters
description: How to ignore certain image defects that may be incorrectly recognized as characters.
keywords:
- blacklist
- symbols
- characters
- letters
- deny
---

Image defects such as dirt and scratches may cause recognition errors. For example, dots or other print defects next to letters can be incorrectly recognized as punctuation or diacritical marks.

To ignore certain characters during recognition, provide them in `ignoredCharacters` property of [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings) as a case-sensitive string:

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set recognition language
RecognitionSettings settings;
settings.ignoredCharacters = L"Áá";
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
