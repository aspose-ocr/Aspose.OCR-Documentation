---
weight: 50
date: "2023-11-24"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/hello-world/
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

In this article, you will learn how to build a bare minimum console application for extracting text from an image with with Aspose.OCR for JavaScript via C++.

{{% alert color="primary" %}} 
We assume that you already have a basic knowledge of **HTML** and **JavaScript**.
{{% /alert %}} 

## You will need

- A [compatible](/ocr/javascript-cpp/system-requirements/) web browser.
- Any text editor.
- Web server to overcome [CORS limitations](/ocr/javascript-cpp/system-requirements/#working-with-local-files). In this article, we will use **Python 3** to run the server.
- Some image containing a text. You can simply download the one from this article.
- **15 minutes** of spare time.

## Preparing

1. Create a folder somewhere on your system where the project files will be kept. For example, `C:\Aspose-JS-Example\`.
2. [Download](https://releases.aspose.com/ocr/javascript-cpp/) Aspose.OCR for JavaScript via C++ and extract it.
3. Copy the contents of `lib` folder of the downloaded Aspose.OCR for JavaScript via C++ package to the root of the project directory:

    - `asposeocr.js` - main JavaScript file;
    - `asposeocr.wasm` - WebAssembly module;
    - `asposeocr.data` - recognition models.

4. Download a sample image:
   
   <img src="source.png" alt="Source image" style="box-shadow: 1px 1px 4px 2px rgba(0,0,0,0.2);margin-top:8px;" />

## Coding

1. Create a simple `index.html` file in the root of the project directory.
   ```html
   <!doctype html>
   <html>
      <head>
         <title>Aspose.OCR for JavaScript via C++</title>
      </head>
      <body>
      </body>
   </html>
   ```

2. Add an input field in which the user can upload an image file and an element to display recognition results to the page body:
   ```html
   <p><b>Provide image file:</b></p>
   <input type="file" id="sourceFile">
   <p><b>Log:</b></p>
   <div id="outputConsole" style="border: solid 1px #cccccc; padding: 10px;"></div>
   ```

3. Reference Aspose.OCR for JavaScript via C++ main script:
   ```html
   <script src="asposeocr.js"></script>
   ```

4. Add a custom script for image processing:
   ```html
   <script>
   var Module = {
      onRuntimeInitialized: function()
      {
         // Initialize interface elements
         const sourceFile = document.getElementById("sourceFile");
         sourceFile.addEventListener("change", handleImgUpload);
         const outputConsole = document.getElementById("outputConsole");
         log("Select an image to continue...");

         // Recognition
         function handleImgUpload(event)
         {
            // Load image file provided by the user
            const file = event.target.files[0];
            log(`Source image: ${file.name}`);
            const reader = new FileReader();
            reader.onload = function(e){
               const fileData = new Uint8Array(e.target.result);
               let filename = file.name;
               let stream = Module.FS.open(filename, "w+");
               Module.FS.write(stream, fileData, 0, fileData.length, 0);
               Module.FS.close(stream);
               // Initialize recognition engine
               var input = Module.WasmAsposeOCRInput();
               var inputs = new Module.WasmAsposeOCRInputs();
               var settings = Module.WasmAsposeOCRRecognitionSettings();
               // Send image file for recognition
               input.url = filename;
               inputs.push_back(input);
               var result = Module.AsposeOCRRecognize(inputs, settings);
               // Get recognition results
               var result_str = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.text);
               // Show recognition results
               log("Recognition result:");
               log(result_str);
            };
            reader.readAsArrayBuffer(file);
            log("Recognition started, please wait...");
         }

         // Logging
         function log(text)
         {
            outputConsole.innerHTML += `<p>${text}</p>`;
         }
      }
   };
   </script>
   ```

## Full code

```html
<!doctype html>
<html>
   <head>
      <title>Aspose.OCR for JavaScript via C++</title>
   </head>
   <body>
      <p><b>Provide image file:</b></p>
      <input type="file" id="sourceFile">
      <p><b>Log:</b></p>
      <div id="outputConsole" style="border: solid 1px #cccccc; padding: 10px;"></div>
      <script>
      var Module = {
         onRuntimeInitialized: function()
         {
            // Interface
            const sourceFile = document.getElementById("sourceFile");
            sourceFile.addEventListener("change", handleImgUpload);
            const outputConsole = document.getElementById("outputConsole");
            log("Select an image to continue...");

            // Recognition
            function handleImgUpload(event)
            {
               const file = event.target.files[0];
               log(`Source image: ${file.name}`);
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
                  var result_str = Module.AsposeOCRSerializeResult(result, Module.ExportFormat.text);
                  log("Recognition result:");
                  log(result_str);
               };
               reader.readAsArrayBuffer(file);
               log("Recognition started, please wait...");
            }

            // Logging
            function log(text)
            {
               outputConsole.innerHTML += `<p>${text}</p>`;
            }
         }
      };
      </script>
      <script src="asposeocr.js"></script>
   </body>
</html>
```

## Running

1. Open the command prompt and navigate to the project folder.
2. Run the web server using Python:
   `python -m http.server 8080`

   If the port 8080 is already occupied, provide a different one.
3. Open `http://localhost:8080/` with a web browser.
4. Select an image and wait for recognition to complete.

You will see extracted text in the `outputConsole` _DIV_ element:

```
Select an image to continue...

Source image: source.png

Recognition started, please wait...

Recognition result:

Hello. World! I can read this text
```

{{% alert color="caution" %}} 
Recognition may take a long time depending on the image size and your system performance, and you may receive “This page is not responding” error.

Ignore the message and wait for recognition to complete.
{{% /alert %}} 

## What's next

Congratulations! You have performed OCR on an image and extracted the machine-readable text from it.
