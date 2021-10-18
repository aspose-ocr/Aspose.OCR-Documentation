---
title: Recognize Array Of Images
type: docs
weight: 32
url: /cpp/array-of-images/
---

## **Recognize array**

Aspose.OCR C++ provides the method [**aspose::ocr::pages_multi_array()**](https://apireference.aspose.com/ocr/cpp/groupAspose#gaf08d9093df5705f826c27ff9ea708ea0)
that allows to recognize a multiple images with one call. The result you will get is array of the wchar_t.

The following code snippet demonstrates the use of the pages_multi_array() method.


[Recognize Array Of Images](/ocr/cpp/array-of-images/)

# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
		const int files_number = 2;
		const char** files = new const char* [files_number];
		files[0] = "../Data/Source/sample.png";
		files[1] = "../Data/Source/sample_line.jpg";
		aspose::ocr::pages_multi_array(files, files_number,  buffer, len, settings);
		std::wcout << buffer;
```


## **Recognize list (C compatible)**

Aspose.OCR C++ allows you to recognize multiple images with a single call by sending a list of images through a semicolon.

The following code snippet demonstrates the use of this feature:

# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
		aspose::ocr::page("folder\\folder1\\image1.png;folder\\folder2\\image2.png", buffer, len);
		std::wcout << buffer;
```
