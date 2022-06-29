---
title: Perform OCR for tables
type: docs
weight: 61
url: /cpp/perform-ocr-for-tables/
---


In case you want to perform OCR operation with better mode for automatic tables cells detection, Aspose.OCR for C++ provides you the following field in 
RecognitionSetting structure: [**detect_areas_mode**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#a23c6ab81de6f8ef6a4e7e84abc79cddd )

detect_areas_mode_enum::TABLE


The following code snippets demonstrate the use of [**detect_areas_mode**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#a23c6ab81de6f8ef6a4e7e84abc79cddd ) TABLE field

## **Perform OCR with different mode for automatic text area detection**

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	const string image = "table.jpg";

	// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096; 
	wchar_t buffer[len] = { 0 };
 
	/* asposeocr_page_settings*/

	RecognitionSettings settings;
    settings.detect_areas_mode = detect_areas_mode_enum::TABLE;
	
    size_t size = asposeocr_page_settings(image.c_str(), buffer, len, settings);
	#ifdef _WIN32
    setmode(_fileno(stdout), 0x00020000);
	#else
    setlocale(LC_CTYPE, "");
	#endif
    std::wcout << buffer;
```