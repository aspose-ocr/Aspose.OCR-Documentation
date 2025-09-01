---
weight: 20
date: "2023-07-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/image-regions-line-find/
feedback: OCRCPP
title: Finding line bounding boxes
description: Automatic detection of line bounding boxes inside an image.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
---

Aspose.OCR allows you to automatically find the coordinates of image rectangles containing text lines. This can be useful for highlighting detected areas when previewing an image or [extracting](/ocr/cpp/image-regions-extract/) individual blocks of text.

To get bounding boxes of all lines of the image, use one of the following functions:

Function | Description
-------- | -----------
`asposeocr_get_rectangles_number()` | Get the total number of paragraphs in the image.
`asposeocr_get_rectangles_number_from_raw_bytes()` | Get the total number of paragraphs in the image provided as an array of pixels.
`asposeocr_get_rectangles_number_from_uri()` | Get the total number of paragraphs in the image provided by URI.<br />This function is not supported in the Linux version of Aspose.OCR for C++.
`asposeocr_get_rectangles()` | Get coordinates of all paragraph in the image. Make sure to use the same parameters as in `asposeocr_get_rectangles_number()` function.
`asposeocr_get_rectangles_from_raw_bytes()` | Get coordinates of all paragraph in the image provided as an array of pixels. Make sure to use the same parameters as in `asposeocr_get_rectangles_number_from_raw_bytes()` function.
`asposeocr_get_rectangles_from_uri()` | Get coordinates of all paragraph in the image provided by URI. Make sure to use the same parameters as in `asposeocr_get_rectangles_number_from_uri()` function.<br />This function is not supported in the Linux version of Aspose.OCR for C++.

Set `type` parameter of the function to `areas_type::lines`.

```cpp
std::string image_path = "source.png";
// calculate the number of lines
size_t res_len = asposeocr_get_rectangles_number(image_path.c_str(), areas_type::lines, false);
std::wcout << "Number of lines: " << res_len << std::endl;
// get line bounding boxes
rect* rectangles = new rect[res_len];
res_len = asposeocr_get_rectangles(image_path.c_str(), areas_type::lines, false, rectangles, res_len);
std::wcout << "lines: " << std::endl;
for (size_t i = 0; i < res_len; i++)
{
	std::wcout << " x: " << rectangles[i].x << " y: " << rectangles[i].y << " width: " << rectangles[i].width << " height: " << rectangles[i].height << std::endl;
}
```

Coordinates of each line (top-left corner, width and height) are returned as an array of [`rect`](https://reference.aspose.com/ocr/cpp/structrect/) objects.

## Important consideration

Line detection works differently depending on the `all_image` parameter of the function:

detectAreas | Behavior
----------- | --------
`true`      | The OCR engine tries to [break the content](/ocr/cpp/areas-detection/) into paragraphs and then extracts lines from the found paragraphs. Best suited for multi-column texts - adjacent lines in different columns will be treated as separate lines rather than a single line.
`false`     | The OCR engine ignores the columns and combines adjacent lines from different columns into a single line. This can be useful when concatenating text from table rows.
