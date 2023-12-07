---
weight: 50
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/areas-detection/curved_text/
title:  Module.DetectAreasMode.CURVED_TEXT
description: How Aspose.OCR for JavaScript via C++ determines the structure of a document using the Module.DetectAreasMode.CURVED_TEXT model.
keywords:
- structure
- region
- area
- photo
- distort
- curve
---

When photographing pages of books and magazine articles, the cylindrical curvature of the page results in distortion of the image, causing the lines of text to curl. This 3D geometric distortion negatively affects recognition.

**Module.DetectAreasMode.CURVED_TEXT** areas detection model uses a specialized neural network that automatically tracks and rectifies curved lines of text. This greatly improves recognition accuracy and allows much more text to be recovered and extracted.

![Detecting and rectifying curved lines of text](curved_text.png)

However, this model is less efficient and consumes more resources when dealing with perfectly straight images, such as a single scanned sheet of paper. Try [**Module.DetectAreasMode.DOCUMENT**](/ocr/javascript-cpp/areas-detection/document/) or [**Module.DetectAreasMode.PHOTO**](/ocr/javascript-cpp/areas-detection/photo/) instead.

## Example

The following code sample demonstrates how to use this document areas detection model:

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.detect_areas_mode = Module.DetectAreasMode.CURVED_TEXT;
```
