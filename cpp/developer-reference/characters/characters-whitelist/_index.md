---
weight: 20
date: "2022-12-08"
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

## Predefined character sets

To define the predefined set of characters Aspose.OCR engine will look for, provide one of the following values in `allowed_characters` property of [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings):

Subset | Action
------ | ------
characters_allowed_type::ALL | Try to recognize all characters.
characters_allowed_type::LATIN_ALPHABET | Only recognize Latin / English text (`A` to `Z` and `a` to `z`), without accented characters. 
characters_allowed_type::DIGITS | Recognize only binary, octal, decimal, or hexadecimal numbers (`0-9` and `A` to `F`).

Characters that do not match the provided subset are ignored.

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.ignoredCharacters = characters_allowed_type::DIGITS;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```

## Custom characters list

You can specify your own list of characters to be recognized. To define the exact set of characters Aspose.OCR engine will look for, use one of the following methods:

- [`page_abc()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga0e6cc74793adbf5efdf4028d7f9161f9),
- [`page_abc_all()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga5e96a883c6923558a138e229cf955be9),
- [`page_abc_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaee6090566975888065f5896b012775ff),
- [`page_abc_all_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga32105a78cbec618e939173e0cf10aec6),
- [`page_rect_abc()`](https://reference.aspose.com/ocr/cpp/groupAspose#gac18245d4e1ca774d564d3a3d834fcd8f),
- [`page_rect_abc_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga03e16bd8c88979916eecde5ca0024f46),
- [`line_abc()`](https://reference.aspose.com/ocr/cpp/groupAspose#gaf65e3c2c22843a71db64571b70ba1a12),
- [`line_abc_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga4b768b17e0ee76582153aeb11f4d2503).

The characters are provided as a _case-sensitive_ string. Characters that do not match the provided list are ignored.

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
size_t size = aspose::ocr::page_abc(image_path.c_str(), buffer, len, L"AÁBCDEÉFG12345");
std::wcout << buffer << L"\n";
```
