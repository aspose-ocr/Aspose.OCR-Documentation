---
weight: 70
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/recognition/
title: Recognition
description: Extracting text from images, web links, archives, and other content.
keywords:
- read
- extract
- OCR
- recognize
---

Reading text from a scanned page, photo, web link or even archive in Aspose.OCR for JavaScript via C++ is as easy as calling a universal `AsposeOCRRecognize()` method.

This method takes a sequence of [`WasmAsposeOCRInput` objects](/ocr/javascript-cpp/content-for-ocr/) and optional [recognition settings](/ocr/javascript-cpp/settings/).

Recognition results are returned as an object, that allow you to [get](/ocr/javascript-cpp/get-results/) extracted text in various [formats](/ocr/javascript-cpp/supported-file-formats/#recognition-results).

## Example

The following code example shows how to extract text from an image uploaded by an user:

```javascript
var Module = {
   onRuntimeInitialized: function()
   {
      // Interface
      const sourceFile = document.getElementById("sourceFile");
      sourceFile.addEventListener("change", handleImgUpload);
      const outputConsole = document.getElementById("outputConsole");

      // Recognition
      function handleImgUpload(event)
      {
         const file = event.target.files[0];
         const reader = new FileReader();
         reader.onload = function(e){
            const fileData = new Uint8Array(e.target.result);
            let filename = file.name;
            let stream = Module.FS.open(filename, "w+");
            Module.FS.write(stream, fileData, 0, fileData.length, 0);
            Module.FS.close(stream);
            var input = Module.WasmAsposeOCRInput();
            var inputs = new Module.WasmAsposeOCRInputs();
            var settings = Module.WasmAsposeOCRRecognitionSettings();
            input.url = filename;
            inputs.push_back(input);
            var result = Module.AsposeOCRRecognize(inputs, settings);
            // Get recognition results as text
            var result_str = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.text);
            console.log(result_str);
         };
         reader.readAsArrayBuffer(file);
      }
   }
};
```
