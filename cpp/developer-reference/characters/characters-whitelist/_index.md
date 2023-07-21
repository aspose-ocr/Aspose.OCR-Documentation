---
weight: 20
date: "2023-07-18"
author: "Vladimir Lapin"
type: docs
url: /cpp/characters-whitelist/
feedback: OCRCPP
aliases:
- /cpp/provide-allowed-characters-during-ocr-operation/
title: Defining the whitelist of characters
description: How to limit the set of characters Aspose.OCR engine will look for.
keywords:
- whitelist
- symbols
- characters
- letters
- allow
---

Limiting a subset of characters instead of using the [full list for a selected language](/ocr/cpp/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption. A list of characters can be automatically [identified](/ocr/cpp/characters-identify/) from an image using the built-in Aspose.OCR mechanisms.

You can define a list of characters Aspose.OCR engine will look for by specifying them as a case-sensitive string in `alphabet` property of [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings). Characters that do not match the provided list are ignored.

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set recognition language
RecognitionSettings settings;
settings.alphabet = L"AÁBCDEÉFG12345";
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::cout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```

Alternatively, you can specify the preset in `allowed_characters` property of [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings):

Preset | Allowed characters
------ | ------------------
`characters_allowed_type::ALL` | All characters.
`characters_allowed_type::LATIN_ALPHABET` | Only recognize Latin / English text (`A` to `Z` and `a` to `z`), without accented characters. 
`characters_allowed_type::DIGITS` | Recognize only binary, octal, decimal, or hexadecimal numbers (`0-9` and `A` to `F`).

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set recognition language
RecognitionSettings settings;
settings.allowed_characters = characters_allowed_type::DIGITS;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::cout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
