---
title: Recognize multi images
type: docs
weight: 30
url: /cpp/folders-and-archives/
---

## **Recognize archive**

Aspose.OCR C++ provides the method [**pages_multi()**](https://apireference.aspose.com/ocr/cpp/) that allows to recognize a multi images with one call. The result you will get is array of the wchar_t.

The following code snippet demonstrates the use of the pages_multi() method.


[Recognize multi images](/ocr/cpp/folders-and-archives/)

# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	// The path to the documents archive (only zip).
	std::string image_path = "../Data/Source/Source.zip";

	// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096;
	wchar_t buffer[len] = { 0 };

	RecognitionSettings settings;//default

	size_t res_len = aspose::ocr::pages_multi(image_path.c_str(), buffer, len, settings);
	std::wcout << buffer;
```


## **Recognize folder**

Aspose.OCR C++ provides the method [**RecognizeMultipleImages**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) that allows to recognize a multi images with one call. The result you will get is array of the [**RecognitionResult**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionresult) class.

The following code snippet demonstrates the use of the [**RecognizeMultipleImages**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) method.


# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	// The path to the documents directory.
	std::string image_path = "../Data/Source";

	// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096;
	wchar_t buffer[len] = { 0 };

	RecognitionSettings settings;//default

	size_t res_len = aspose::ocr::pages_multi(image_path.c_str(), buffer, len, settings);
	std::wcout << buffer;
```
