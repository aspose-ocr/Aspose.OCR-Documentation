---
weight: 40
date: "2023-12-14"
author: "Vladimir Lapin"
type: docs
url: /nodejs-cpp/hello-world/
title: Hello, world!
description: Get started with Aspose.OCR for C++ by creating and running a bare minimum example.
keywords:
- hello world
- evaluation
- example
- sample
- dummies
- code
---

In this article, you will learn how to build a basic web page that requests an image file from an user and extracts the text from it with with Aspose.OCR for Node.js via C++.

{{% alert color="primary" %}} 
We assume that you are already familiar with core concepts of **Node.js** development and have a basic knowledge of **JavaScript** language.
{{% /alert %}} 

## You will need

- A computer with [Node.js 14 or later](/ocr/nodejs-cpp/system-requirements/).
- Any text editor.
- Some image containing a text. You can simply download the one from this article.
- **15 minutes** of spare time.

## Preparing

1. Create a directory somewhere on your system where the project files will be kept. For example, `C:\Aspose-OCR-Example\`.  
   This directory will later be referred as _project directory_.
2. Create **node_modules** directory in the project directory.
3. [Download](https://releases.aspose.com/ocr/nodejs-cpp/) Aspose.OCR for Node.js via C++ distributive.
4. Unpack the [downloaded package](/ocr/nodejs-cpp/installation/) to **aspose-ocr** directory inside **node_modules** directory.
5. Download a sample image to the project directory under the name `source.png`:
   
   <img src="source.png" alt="Source image" style="box-shadow: 1px 1px 4px 2px rgba(0,0,0,0.2);margin-top:8px;" />

## Coding

1. Create an `index.js` file in the the project directory which will be used as a main (startup) project script.
2. Import Aspose.OCR and [File system](https://nodejs.org/api/fs.html) modules:
   ```js
   const Module = require("aspose-ocr/lib/asposeocr");
   const fs = require("fs");
   ```

3. Start recognition once Aspose.OCR for Node.js via C++ module finishes loading:  

   ```js
   Module.onRuntimeInitialized = async _ => {
   }
   ```

4. Load the image into the project's temporary storage:  

   ```js
   fs.readFile("source.png", (err, imageData) => {
      const imageBytes = new Uint8Array(imageData);
      let internalFileName = "temp";
      let stream = Module.FS.open(internalFileName, "w+");
      Module.FS.write(stream, imageBytes, 0, imageBytes.length, 0);
      Module.FS.close(stream);
   });
   ```

   {{% alert color="primary" %}}
   Aspose.OCR for Node.js via C++ binary code is based on WebAssembly (Wasm) technology. As such, it has no access to physical files on disks and uses the virtual file system.

   To overcome this restriction, we read the image file to the array of bytes and then save it to the virtual file system of Aspose.OCR module.
   {{% /alert %}}

5. Add the image to the recognition batch:  

   ```js
   let source = Module.WasmAsposeOCRInput();
   source.url = internalFileName;
   let batch = new Module.WasmAsposeOCRInputs();
   batch.push_back(source);
   ```

6. Specify the [recognition language](/ocr/nodejs-cpp/recognition-languages/):  

   ```js
   let recognitionSettings = Module.WasmAsposeOCRRecognitionSettings();
   recognitionSettings.language_alphabet = Module.Language.ENG;
   ```

7. Send image for recognition:  

   ```js
   var result = Module.AsposeOCRRecognize(batch, recognitionSettings);
   ```

8. Output image text to the console:  

   ```js
   var text = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.text);
   console.log(text);
   ```


### Full listing (_index.js_)

```js
const Module = require("aspose-ocr/lib/asposeocr");
const fs = require("fs");

Module.onRuntimeInitialized = async _ => {
   // Load image file
   fs.readFile("source.png", (err, imageData) => {
      // Save image to the virtual storage
      const imageBytes = new Uint8Array(imageData);
      let internalFileName = "temp";
      let stream = Module.FS.open(internalFileName, "w+");
      Module.FS.write(stream, imageBytes, 0, imageBytes.length, 0);
      Module.FS.close(stream);
      // Add image to recognition batch
      let source = Module.WasmAsposeOCRInput();
      source.url = internalFileName;
      let batch = new Module.WasmAsposeOCRInputs();
      batch.push_back(source);
      // Specify recognition language
      let recognitionSettings = Module.WasmAsposeOCRRecognitionSettings();
      recognitionSettings.language_alphabet = Module.Language.ENG;
      // Send image for OCR
      var result = Module.AsposeOCRRecognize(batch, recognitionSettings);
      // Output image text to the console
      var text = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.text);
      console.log(text);
   });
}
```

## Running

1. Open the command prompt and navigate to the project directory.
2. Run **index.js** script with the following command:  
   `node --no-experimental-fetch index`
3. Wait for recognition to complete. It may take a while depending on the image size and your system performance.

You will see extracted text in the console output:

```
Hello. World! I can read this text
```

## What's next

Congratulations! You have performed OCR on an image and extracted the machine-readable text from it using Node.js.
