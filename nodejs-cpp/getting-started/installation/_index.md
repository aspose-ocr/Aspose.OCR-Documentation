---
weight: 20
date: "2023-12-11"
author: "Vladimir Lapin"
type: docs
url: /nodejs-cpp/installation/
title: Installation
description: Adding or updating Aspose.OCR for Node.js via C++ package in your web app.
keywords:
- install
- update
- package
- download
---

**Aspose.OCR for Node.js via C++** is distributed as a [downloadable package](https://releases.aspose.com/ocr/nodejs-cpp/).

## Installing the library

1. [Download](https://releases.aspose.com/ocr/nodejs-cpp/) the latest version of the package.
2. Unpack the downloaded archive somewhere on your system.
3. Copy the following files from **lib** directory of the downloaded archive and place them in the same directory as the main script of your project:

    - _asposeocr.js_ (Aspose.OCR for Node.js via C++ core code)
    - _asposeocr.wasm_ (binary)
    - _asposeocr.data_ (recognition models)

4. Import Aspose.OCR for Node.js via C++ module in your code:  

   ```js
   const Module = require("./asposeocr");
   ```

## Updating the library

To update Aspose.OCR for Node.js via C++ to the new version:

1. [Download](https://releases.aspose.com/ocr/nodejs-cpp/) the latest version of the package.  
   Check the [Release Notes](https://releases.aspose.com/ocr/nodejs-cpp/release-notes/) to ensure the downloaded version is backwards compatible with the existing code.
2. Unpack the downloaded archive somewhere on your system.
2. Copy the following files from **lib** directory of the downloaded archive and place them in the same directory as the web page, replacing the existing files:

    - _asposeocr.js_ (Aspose.OCR for Node.js via C++ core code)
    - _asposeocr.wasm_ (binary)
    - _asposeocr.data_ (recognition models)
