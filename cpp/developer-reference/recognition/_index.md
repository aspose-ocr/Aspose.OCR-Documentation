---
weight: 70
date: "2023-07-18"
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

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for C++ 23.3.0, this function replaces `asposeocr_page()`, `asposeocr_page_settings()`, `asposeocr_page_all()`, `asposeocr_page_abc()`, `asposeocr_page_abc_all()`, `asposeocr_page_tiff()`, `asposeocr_page_from_uri()`, `asposeocr_pages_multi()`, `asposeocr_pages_multi_array()`, `asposeocr_pages_multi_array_from_raw_bytes()`, `asposeocr_page_from_raw_bytes()`, `asposeocr_page_settings_from_raw_bytes()`, `asposeocr_page_all_from_raw_bytes()`, `asposeocr_page_abc_from_raw_bytes()`, `asposeocr_page_abc_all_from_raw_bytes()`, `asposeocr_page_rect()`, `asposeocr_page_rect_from_raw_bytes()`, `asposeocr_page_rect_abc()`, and `asposeocr_page_rect_abc_from_raw_bytes()` functions.
{{% /alert %}}

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
std::cout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
