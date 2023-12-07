---
weight: 40
date: "2023-12-07"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/save-xml/
title: Getting recognition results as XML
description: Returning Aspose.OCR for JavaScript via C++ recognition results in XML format.
keywords:
- save
- result
- XML
- output
---

Aspose.OCR for JavaScript via C++ can return recognition results as XML - a universal data exchange and storage format. To get recognition results in XML format, call `AsposeOCRSerializeResult()` method. Provide the recognition result returned from [recognition function](/ocr/javascript-cpp/recognition/) and `Module.ExportFormat.xml` (`2`) value as method parameters.

```javascript
var input = Module.WasmAsposeOCRInput();
var inputs = new Module.WasmAsposeOCRInputs();
input.url = filename;
inputs.push_back(input);
// Recognize
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.language_alphabet = Module.Language.deu;
var result = Module.AsposeOCRRecognize(inputs, settings);
// Get recognition results as XML
var result_xml = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.xml);
console.log(result_xml);
```
