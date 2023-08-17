---
weight: 10
date: "2023-08-17"
author: "Vladimir Lapin"
type: docs
url: /cpp/content-for-ocr/
feedback: OCRCPP
title: Preparing content for recognition
description: How to prepare a batch of images, PDF documents, URLs and other content for recognition.
keywords:
- image
- PDF
- file
- folder
- batch
- list
---

Aspose.OCR for C++ provides a standardized way to prepare your content for OCR. The image, document, folder, or URL is provided as an `AsposeOCRInput` structure. Multiple `AsposeOCRInput` structures are encapsulated into `std::vector` sequence container allowing you to easily process a single image or a large number of images (for example, pages from an auto-feed scanner) with a single API call.

## Supported content types

Depending on the content type, you should set different `AsposeOCRInput` structure members:

Content type | Required structure members
------------ | --------------------------
File (of any [supported format](/ocr/cpp/supported-file-formats/)) | <ul><li>`url` - provide an absolute or relative path to the source file.</li></ul>
Directory | <ul><li>`url` - provide an absolute or relative path to the directory with images and PDF documents. Sub-directories will be ignored.</li></ul>
URL | <ul><li>`url` - provide a public URL to an image or PDF document.</li></ul>
Raw image data | <ul><li>`raw_data` - provide an image as [raw bytes or pixels](/ocr/cpp/content-for-ocr/image-by-bytes/).</li><li>`width` - image width, in pixels (only required when providing an image as pixel array).</li><li>`height` - image height, in pixels (only required when providing an image as pixel array).</li><li>`raw_data_size` - size of the `raw_data` member.</li><li>`raw_data_type` - image color model (when providing an image as pixel array) or file format (when providing an image file as byte array).</li></ul>

{{% alert color="caution" %}}
You must choose whether to provide content as a path/URL or as raw pixel data. For other elements of the structure, you must leave the default values.

Providing both content types in the same structure will result in an error. However, you can put multiple `AsposeOCRInput` structures are into `std::vector` sequence.
{{% /alert %}}

## Examples

The following code samples demonstrates how to prepare content for recognition:

{{< tabs tabID="1" tabTotal="3" tabName1="Provide multiple images" tabName2="Provide scanned PDF" tabName3="Provide an URL" >}}
{{< tab tabNum="1" >}}
```cpp
// First image
string file1 = current_dir + "/page1.png";
AsposeOCRInput source1;
source1.url = file1.c_str();
// Second image
string file2 = current_dir + "/page2.png";
AsposeOCRInput source2;
source2.url = file2.c_str();
// Encapsulate images
std::vector<AsposeOCRInput> content = { source1, source2 };
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```cpp
string file = current_dir + "/source.pdf";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```cpp
string link = "https://upload.wikimedia.org/wikipedia/commons/e/e4/Biggle_horse_book_%28Page_45%29_BHL23865068.jpg";
AsposeOCRInput source;
source.url = link.c_str();
std::vector<AsposeOCRInput> content = { source };
```
{{< /tab >}}
{{< /tabs >}}
