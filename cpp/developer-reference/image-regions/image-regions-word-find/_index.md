---
weight: 30
date: "2022-12-10"
author: "Vladimir Lapin"
type: docs
url: /cpp/image-regions-word-find/
title: Finding word bounding boxes
description: Automatic detection of word bounding boxes inside an image.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
---

Aspose.OCR allows you to automatically find the coordinates of image rectangles containing text words. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/cpp/image-regions-extract/) individual blocks of text.

To get bounding boxes of all words of the image, use one of the following methods:

Method | Description
------ | -----------
[`get_rectangles_number()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga915d8b416a56c5512c81677a5e29ba5c) | Get the total number of words in the image.
[`get_rectangles_number_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga2974731f43466e0b53bc721c15f5835a) | Get the total number of words in the image provided as an array of pixels.
[`get_rectangles_number_from_uri()`](https://reference.aspose.com/ocr/cpp/groupAspose#gafa06a729340a98aed1345d2b329b8ace) | Get the total number of words in the image provided by URI.<br />This method is not supported in the Linux version of Aspose.OCR for C++.
[`get_rectangles()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga678ce5134a3af65992a99da963bcf3dd) | Get coordinates of all word in the image. Make sure to use the same parameters as in `get_rectangles_number()` method.
[`get_rectangles_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#gad2f4783815cac578ec80230c5aea4d8f) | Get coordinates of all word in the image provided as an array of pixels. Make sure to use the same parameters as in `get_rectangles_number_from_raw_bytes()` method.
[`get_rectangles_from_uri()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga270c57b8595cd911c7cf2e68fcc624af) | Get coordinates of all word in the image provided by URI. Make sure to use the same parameters as in `get_rectangles_number_from_uri()` method.<br />This method is not supported in the Linux version of Aspose.OCR for C++.

Set `type` parameter of the method to `areas_type::words`.

```cpp
std::string image_path = "source.png";
// calculate the number of words
size_t res_len = aspose::ocr::get_rectangles_number(image_path.c_str(), areas_type::words, false);
std::wcout << "Number of words: " << res_len << std::endl;
// get word bounding boxes
rect* rectangles = new rect[res_len];
res_len = aspose::ocr::get_rectangles(image_path.c_str(), areas_type::words, false, rectangles, res_len);
std::wcout << "words: " << std::endl;
for (size_t i = 0; i < res_len; i++)
{
	std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
}
```

Coordinates of each word (top-left corner, width and height) are returned as an array of [`rect`](https://reference.aspose.com/ocr/cpp/structrect/) objects.
