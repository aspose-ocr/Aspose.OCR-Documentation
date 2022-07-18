---
title: Custom Image Correction Using Threshold Setting
type: docs
weight: 75
url: /cpp/custom-image-correction-with-threshold-setting/
---
## **Custom Image Correction Using Threshold Setting**
Aspose.OCR.Cpp provides to option to specify custom threshold value for image quality correction. 
For this, the API provides the [**RecognitionSettings.threshold_value**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a31c7ff65781feffc6e79887afc7b395f) property. 
You can pass the instance of the [**RecognitionSettings**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings) structure
to the [**page_settings()**](https://reference.aspose.com/ocr/cpp/groupAspose#ga028cce64d935cf8fc8d5eab3d3713ebf) method.

The following code snippet demonstrates the use of the [**RecognitionSettings.threshold_value**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a31c7ff65781feffc6e79887afc7b395f)
property provides custom image quality correction. 
Usually, threshold value calculated automatically, but in some cases, using [**RecognitionSettings.threshold_value**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a31c7ff65781feffc6e79887afc7b395f)
property can get better recognition result. You can customize it from 1 to 255 value.
 If you set  the [**RecognitionSettings.threshold_value**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings#a31c7ff65781feffc6e79887afc7b395f) as 0 (zero), 
 this value will be calculated automatically.


## Sample Code

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	directory dir(".");
    const string current_dir = "";
    const string image = current_dir + "1.png";
    const size_t len = 4096;
    wchar_t buffer[len] = { 0 };

    RecognitionSettings settings;
    settings.threshold_value = 70;
    size_t size = asposeocr_page_settings(image.c_str(), buffer, len, settings);
#ifdef _WIN32
    setmode(_fileno(stdout), 0x00020000);
#else
    setlocale(LC_CTYPE, "");
#endif
    std::wcout << buffer;
```

