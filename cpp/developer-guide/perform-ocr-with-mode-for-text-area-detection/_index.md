---
title: Perform OCR with different modes for automatic text area detection
type: docs
weight: 61
url: /cpp/perform-ocr-with-mode-for-text-area-detectionn/
---


In case you want to perform OCR operation with better mode for automatic text area detection, Aspose.OCR for C++ provides you the following field in 
RecognitionSetting structure: [**detect_areas_mode**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a23c6ab81de6f8ef6a4e7e84abc79cddd )

detect_areas_mode_enum::NONE : Perform OCR operation on an image without automatically detecting the text area.
detect_areas_mode_enum::DOCUMENT : Detects paragraphs uses NN model for documents. Better for multicolumn document, document with pictures or with other not text objects.
detect_areas_mode_enum::PHOTO : Detects paragraphs uses NN model for photos. Better for image with a lot of pictures and other not text objects.
detect_areas_mode_enum::COMBINE : Detects paragraphs with text and then uses other NN model to detect areas inside of paragraphs. Better for images with complex structure.


The following code snippets demonstrate the use of [**detect_areas_mode**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a23c6ab81de6f8ef6a4e7e84abc79cddd ) field

## **Perform OCR with different mode for automatic text area detection**

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	const string image = "img.jpg";

	// Prepare buffer for result (in symbols, len_byte = len * sizeof(wchar_t))
	const size_t len = 4096; 
	wchar_t buffer[len] = { 0 };
 
	/* asposeocr_page_settings*/

	RecognitionSettings settings;
    settings.detect_areas_mode = detect_areas_mode_enum::COMBINE;
	
    size_t size = asposeocr_page_settings(image.c_str(), buffer, len, settings);
	#ifdef _WIN32
    setmode(_fileno(stdout), 0x00020000);
	#else
    setlocale(LC_CTYPE, "");
	#endif
    std::wcout << buffer;
```