---
weight: 20
date: "2023-12-04"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/characters-whitelist/
title: Defining the whitelist of characters
description: How to limit the set of characters Aspose.OCR engine will look for.
keywords:
- whitelist
- symbols
- characters
- letters
- allow
---

Limiting a subset of characters instead of using the [full list for a selected language](/ocr/javascript-cpp/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption.

You can define a list of characters Aspose.OCR engine will look for by specifying them as a case-sensitive string in `alphabet` property of [recognition settings](/ocr/javascript-cpp/settings/). Characters that do not match the provided list are ignored.

```javascript
// Prepare images
var source = Module.WasmAsposeOCRInput();
source.url = filename;
var content = new Module.WasmAsposeOCRInputs();
content.push_back(source);
// Limiting characters to be identified
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.alphabet = "AÁBCDEÉFG12345";
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```

Alternatively, you can specify the predefined collection of characters in `allowed_characters` property of [recognition settings](/ocr/javascript-cpp/settings/). It will make your code more readable when working with massive whitelists.

Preset | Numeric value | Allowed characters
------ | ------------- | ------------------
`Module.CharactersAllowedType.ALL` | 0 | Recognize all characters.
`Module.CharactersAllowedType.LATIN_ALPHABET` | 1 | Only recognize case-insensitive Latin / English text (`A` to `Z` and `a` to `z`), without accented characters, punctuation, numbers, end the like. 
`Module.CharactersAllowedType.DIGITS` | 2 | Recognize only binary, octal, decimal, or hexadecimal numbers (`0-9` and `A` to `F`).

```javascript
// Prepare images
var source = Module.WasmAsposeOCRInput();
source.url = filename;
var content = new Module.WasmAsposeOCRInputs();
content.push_back(source);
// Instruct OCR engine to recognize numbers only
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.allowed_characters = Module.CharactersAllowedType.DIGITS;
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```
