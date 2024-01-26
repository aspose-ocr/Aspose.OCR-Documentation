---
weight: 70
date: "2024-01-25"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognition/
aliases:
- /cpp/recognition/image/
- /cpp/perform-ocr-on-an-image/
- /cpp/recognition/tiff/
- /cpp/recognize-multipage-tiff/
- /cpp/recognition/url/
- /cpp/performing-ocr-on-an-image-from-url/
- /cpp/recognition/pixel/
- /cpp/batch-recognition/
- /cpp/array-of-images/
- /cpp/folders-and-archives/
feedback: OCRCPP
title: Recognition
description: Extracting text from images, web links, scanned PDFs, folders, and other content.
keywords:
- read
- extract
- OCR
- recognize
---

Reading text from any content in Aspose.OCR for C++ is as easy as calling a universal `asposeocr_recognize()` function.

This function takes a sequence of [`OcrInput` objects](/ocr/cpp/ocrinput/) and optional [recognition settings](/ocr/cpp/recognition-settings-common/).

Recognition results are returned as a `AsposeOCRRecognitionResult` structure, that allow you to get image text and [save](/ocr/cpp/save/) results in various formats.

## Releasing resources

Once you have performed all the required operations with the `AsposeOCRRecognitionResult` structure, it is recommended to release the allocated memory by calling `asposeocr_free_result()` function.

## Example

The following code example shows how to extract text from multiple images:

```cpp
// Provide images
string file = "page1.png";
AsposeOCRInput source1;
source1.url = file.c_str();
string file = "page2.png";
AsposeOCRInput source2;
source2.url = file.c_str();
std::vector<AsposeOCRInput> content = { source1, source2 };
// Fine-tune recognition
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
