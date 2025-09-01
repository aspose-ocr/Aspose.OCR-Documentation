---
weight: 30
date: "2023-12-07"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/save-json/
title: Getting recognition results as JSON
description: Returning Aspose.OCR for JavaScript via C++ recognition results in JSON format.
keywords:
- save
- result
- JSON
- output
---

Aspose.OCR for JavaScript via C++ can return recognition results in JSON format - de facto data exchange standard for websites and REST APIs. To get recognition results in JSON format, call `AsposeOCRSerializeResult()` method. Provide the recognition result returned from [recognition function](/ocr/javascript-cpp/recognition/) and `Module.ExportFormat.json` (`1`) value as method parameters.

```javascript
var input = Module.WasmAsposeOCRInput();
var inputs = new Module.WasmAsposeOCRInputs();
input.url = filename;
inputs.push_back(input);
// Recognize
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.language_alphabet = Module.Language.DEU;
var result = Module.AsposeOCRRecognize(inputs, settings);
// Get recognition results as JSON
var result_json = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.json);
console.log(result_json);
```
