---
title: Image preprocessing
type: docs
weight: 31
url: /cpp/image-preprocessing/
---

## **Preprocess image C-compatible API**

Aspose.OCR C++ provides the method [**asposeocr_preprocess_page_and_save()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga69cc8aa64a4cd77628f3b273c3d41645) 
that allows to preprocess image with different filters. The result you will get as new image in your filesystem.

The following code snippet demonstrates the use of the preprocess_page_and_save() method.


[preprocess image](/ocr/cpp/image-preprocessing-c/)

# Sample Code 

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	
	
	custom_preprocessing_filters filters_;
    filters_.filter_1 = OCR_IMG_PREPROCESS_INVERT;
    filters_.filter_2 = OCR_IMG_PREPROCESS_THRESHOLD(20);
	filters_.filter_3 = OCR_IMG_PREPROCESS_BINARIZE;
    filters_.filter_4 = OCR_IMG_PREPROCESS_RESIZE(1000, 1000);
    filters_.filter_5 = OCR_IMG_PREPROCESS_SCALE(0.3);
    filters_.filter_6 = OCR_IMG_PREPROCESS_DILATE;
    filters_.filter_7 = OCR_IMG_PREPROCESS_ROTATE(-20);
    filters_.filter_8 = OCR_IMG_PREPROCESS_GRAYSCALE;
    asposeocr_preprocess_page_and_save(image.c_str(), "output_img_name.png", filters_);
```


## **Preprocess image C++ -compatible API**

Aspose.OCR C++ provides the method [**preprocess_page_and_save()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga056fd7bc1e4fc540bb14b3f83994b5d6) 
that allows to preprocess image with different filters. The result you will get as new image in your filesystem.

The following code snippet demonstrates the use of the preprocess_page_and_save() method.


[preprocess image](/ocr/cpp/image-preprocessing-c-plus/)

# Sample Code 

```cpp
	std::vector<filter_operation> filters;
    filters.push_back(OCR_IMG_Resize(1000,1000));
    filters.push_back(OCR_IMG_Scale(0.3));
    filters.push_back(OCR_IMG_Invert());
    filters.push_back(OCR_IMG_Threshold(20));
    filters.push_back(OCR_IMG_Rotate(10));
	filters.push_back(OCR_IMG_Grayscale());
	filters.push_back(OCR_IMG_Dilate());

    aspose::ocr::preprocess_page_and_save(image.c_str(), "output_img_name.png", filters);
```

## **Preprocess and recognize image in one step**

Aspose.OCR C++ provides the field in  [**RecognitionSettings**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#a357319e06844393ae68e9af538835755) 
that allows to preprocess image with different filters before text recognition. The preprocessed image will be sent for recognition.

The following code snippet demonstrates the use of the custom_preprocessing_filters RecognitionSettings::filters fileld:


[preprocess image](/ocr/cpp/image-preprocessing-recognition/)

# Sample Code 

```cpp
// Prepare buffer for result 
	const size_t len = 4096;
    wchar_t buffer[len] = { 0 };
// Set filters
	custom_preprocessing_filters filters__;
    filters__.filter_1 = OCR_IMG_PREPROCESS_INVERT;
    filters__.filter_2 = OCR_IMG_PREPROCESS_THRESHOLD(20);
	filters__.filter_3 = OCR_IMG_PREPROCESS_GRAYSCALE;
    filters__.filter_4 = OCR_IMG_PREPROCESS_RESIZE(1000, 1000);
    filters__.filter_5 = OCR_IMG_PREPROCESS_SCALE(0.3);

	RecognitionSettings settings;
	settings.filters = filters__;
	
	size_t res = asposeocr_page_settings(image.c_str(), buffer, len, settings);
	std::wcout << buffer;
```
