---
weight: 30
date: "2023-12-04"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/characters-blacklist/
title: Defining the blacklist of characters
description: How to ignore certain image defects that may be incorrectly recognized as characters.
keywords:
- blacklist
- symbols
- characters
- letters
- deny
---

Image defects such as dirt and scratches may cause recognition errors. For example, spots, noise or other print defects next to letters can be incorrectly recognized as punctuation or diacritical marks.

To ignore certain characters during recognition, provide them in `ignoredCharacters` property of [recognition settings](/ocr/javascript-cpp/settings/) as a case-sensitive string:

```javascript
// Prepare images
var source = Module.WasmAsposeOCRInput();
source.url = filename;
var content = new Module.WasmAsposeOCRInputs();
content.push_back(source);
// Block diacritics recognition
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.ignoredCharacters = L"Áá";
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```
