---
weight: 10
date: "2023-12-04"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/content-for-ocr/
title: Preparing content for recognition
description: How to prepare a batch of images, URLs and other content for recognition.
keywords:
- image
- file
- zip
- archive
- batch
- list
---

Aspose.OCR for JavaScript via C++ provides a standardized way to prepare your content for OCR. Scanned page, photo, image URL, or ZIP archive is loaded to `WasmAsposeOCRInput` object.

Multiple `WasmAsposeOCRInput` objects are encapsulated into `WasmAsposeOCRInputs` sequence container allowing you to easily process a single image or a large number of images (for example, pages from an auto-feed scanner) with a single API call. Each content object is added to the collection using `push_back()` method.

Path to the content is provided in the `url` property of a `WasmAsposeOCRInput` object. The following code example shows how to prepare a file, uploaded by the user via an input field, for recognition:

```javascript
// Initialize file reader
const reader = new FileReader();
// Get image from the user
const file = event.target.files[0];
reader.readAsArrayBuffer(file);
// Process image
reader.onload = function(e) {
	// Write image file to the temporary storage
	const fileData = new Uint8Array(e.target.result);
	let filename = file.name;
	let stream = Module.FS.open(filename, "w+");
	Module.FS.write(stream, fileData, 0, fileData.length, 0);
	Module.FS.close(stream);
	// Load image to Aspose.OCR object
	var source = Module.WasmAsposeOCRInput();
	source.url = filename;
	// Initialize the collection of files
	var content = new Module.WasmAsposeOCRInputs();
	// Add the image to content collection
	content.push_back(source);
};
```
