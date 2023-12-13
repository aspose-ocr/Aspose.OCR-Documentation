---
weight: 20
date: "2023-12-07"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/save-text/
title: Getting recognition results as text
description: Returning Aspose.OCR for JavaScript via C++ recognition results as formatted text.
keywords:
- save
- result
- text
- txt
- output
---

Recognition results in plain text with line breaks are returned from `AsposeOCRSerializeResult()` method. This method takes the recognition result returned from [recognition function](/ocr/javascript-cpp/recognition/) and `Module.ExportFormat.text` (`0`) value.

```javascript
var input = Module.WasmAsposeOCRInput();
var inputs = new Module.WasmAsposeOCRInputs();
input.url = filename;
inputs.push_back(input);
// Recognize
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.language_alphabet = Module.Language.DEU;
var result = Module.AsposeOCRRecognize(inputs, settings);
// Get recognition results as text
var result_str = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.text);
console.log(result_str);
```
