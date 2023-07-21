---
weight: 50
date: "2022-07-19"
author: "Vladimir Lapin"
type: docs
url: /cpp/areas-detection/curved_text/
feedback: OCRCPP
title:  detect_areas_mode_enum::CURVED_TEXT
description: How Aspose.OCR determines the structure of a document using the detect_areas_mode_enum::CURVED_TEXT algorithm.
keywords:
- structure
- region
- area
- photo
- distort
- curve
---

When photographing pages of books and magazine articles, the cylindrical curvature of the page results in distortion of the image, causing the lines of text to curl. This 3D geometric distortion negatively affects recognition.

**detect_areas_mode_enum::CURVED_TEXT** areas detection mode uses a specialized neural network that automatically tracks and rectifies curved lines of text. This greatly improves recognition accuracy and allows much more text to be recovered and extracted.

![Detecting and rectifying curved lines of text](curved_text.png)

However, this algorithm is less efficient and consumes more resources when dealing with perfectly straight images, such as a single scanned sheet of paper. Try [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) or [**detect_areas_mode_enum::PHOTO**](/ocr/cpp/areas-detection/photo/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Fine-tune recognition
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::CURVED_TEXT;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::cout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
