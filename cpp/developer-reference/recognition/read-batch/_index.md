---
weight: 60
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/batch-recognition/
feedback: OCRCPP
aliases:
- /cpp/array-of-images/
- /cpp/folders-and-archives/
title: Batch recognition
description: How to read text from a multiple raster images, folder, or ZIP archive.
keywords:
- read
- extract
- OCR
- recognize
- multiple
- batch
- archive
- folder
---

Aspose.OCR for C++ can read up to **20** PNG, JPEG or BMP images in a single call. Images are be provided as a list of files, a folder, or a ZIP archive. Use one of the following methods:

Method | Description
------ | -----------
[`pages_multi()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga53d926b03a01f388d59801979e21b12c) | Read all images from a folder or a ZIP archive. Subfolders and nested archives are not supported.
[`pages_multi_array()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga81ed44d176a8c54628e309c8acdd8ec0) | Read images provided as an array or paths.
[`pages_multi_array_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga720c8269b71ae31545a1f985071aff15) | Read images provided as pixel arrays.


These methods allow you to optionally customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

{{< tabs tabID="1" tabTotal="2" tabName1="Read images from ZIP achive" tabName2="Read images from folder" tabName3="Read images from array" >}}
{{< tab tabNum="1" >}}
```cpp
std::string image_path = "source.zip";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
size_t res_len = aspose::ocr::pages_multi(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```cpp
std::string image_path = "../book/pages";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
size_t res_len = aspose::ocr::pages_multi(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
{{< /tab >}}
{{< tab tabNum="3" >}}
```cpp
const int files_number = 2;
const char** files = new const char* [files_number];
files[0] = "../book/pages/page1.png";
files[1] = "../book/pages/page2.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
aspose::ocr::pages_multi_array(files, files_number, buffer, len, settings);
std::wcout << buffer;
```
{{< /tab >}}
{{< /tabs >}}
