---
weight: 10
date: "2023-07-19"
author: "Vladimir Lapin"
type: docs
url: /cpp/image-regions-paragraph-find/
feedback: OCRCPP
title: Finding paragraph bounding boxes
description: Automatic detection of paragraph bounding boxes inside an image.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
---

Aspose.OCR allows you to automatically find the coordinates of image rectangles containing text paragraphs. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/cpp/image-regions-extract/) individual blocks of text.

To get bounding boxes of all paragraphs of the image, use one of the following functions:

Function | Description
-------- | -----------
`asposeocr_get_rectangles_number()` | Get the total number of paragraphs in the image.
`asposeocr_get_rectangles_number_from_raw_bytes()` | Get the total number of paragraphs in the image provided as an array of pixels.
`asposeocr_get_rectangles_number_from_uri()` | Get the total number of paragraphs in the image provided by URI.<br />This function is not supported in the Linux version of Aspose.OCR for C++.
`asposeocr_get_rectangles()` | Get coordinates of all paragraph in the image. Make sure to use the same parameters as in `asposeocr_get_rectangles_number()` function.
`asposeocr_get_rectangles_from_raw_bytes()` | Get coordinates of all paragraph in the image provided as an array of pixels. Make sure to use the same parameters as in `asposeocr_get_rectangles_number_from_raw_bytes()` function.
`asposeocr_get_rectangles_from_uri()` | Get coordinates of all paragraph in the image provided by URI. Make sure to use the same parameters as in `asposeocr_get_rectangles_number_from_uri()` function.<br />This function is not supported in the Linux version of Aspose.OCR for C++.

Set `type` parameter of the function to `areas_type::paragraphs`.

```cpp
std::string image_path = "source.png";
// calculate the number of paragraphs
size_t res_len = asposeocr_get_rectangles_number(image_path.c_str(), areas_type::paragraphs, false);
std::wcout << "Number of paragraphs: " << res_len << std::endl;
// get paragraph bounding boxes
rect* rectangles = new rect[res_len];
res_len = asposeocr_get_rectangles(image_path.c_str(), areas_type::paragraphs, false, rectangles, res_len);
std::wcout << "Paragraphs: " << std::endl;
for (size_t i = 0; i < res_len; i++)
{
	std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
}
```

Coordinates of each paragraph (top-left corner, width and height) are returned as an array of [`rect`](https://reference.aspose.com/ocr/cpp/structrect/) objects.
