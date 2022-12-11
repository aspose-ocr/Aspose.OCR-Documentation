---
weight: 30
date: "2022-12-08"
author: "Vladimir Lapin"
type: docs
url: /cpp/characters-blacklist/
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
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.ignoredCharacters = L"Áá";
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
