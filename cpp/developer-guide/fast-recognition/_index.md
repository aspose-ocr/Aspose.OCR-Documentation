---
title: Fast recognition
type: docs
weight: 31
url: /cpp/fast-recognition/
---

## **Recognize without skew correction and areas detection**

Aspose.OCR C++ provides the method [**page_fast()**](https://apireference.aspose.com/ocr/cpp/) 
that allows to recognize an images with fastest mode. It works without skew correction and areas detection
and only for latin alphabet. 
The result you will get is an array of the wchar_t.

The following code snippet demonstrates the use of the page_fast() method.


[Fast Recognition]


# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	// The path to the image.
	std::string image_path = "../Data/Source/Source.img";

	// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096;
	wchar_t buffer[len] = { 0 };

	aspose::ocr::page_fast(image_path.c_str(), buffer, len);
	std::wcout << buffer;
```
