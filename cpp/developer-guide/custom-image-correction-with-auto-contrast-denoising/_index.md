---
title: Custom Image Correction With Auto Contrast Or With Denoising
type: docs
weight: 75
url: /cpp/custom-image-correction-with-auto-contrast-denoising/
---

Image preprocessing operations do in our API automatically, but in some cases, using [**RecognitionSettings.auto_contrast**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings/ ) or [**RecognitionSettings.auto_denoising**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings/ )
property can get better recognition result.

## **Custom Image Correction Using Auto Contrast**
Aspose.OCR.Cpp provides the ability to increase contrast to correct image quality.
For this, the API provides the [**RecognitionSettings.auto_contrast**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings) structure
to the [**page_settings()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga028cce64d935cf8fc8d5eab3d3713ebf) method.

The following code snippet demonstrates the use of the [**RecognitionSettings.auto_contrast**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/)
property provides custom image quality correction. 


## Sample Code

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	directory dir(".");
    const string current_dir = "";
    const string image = current_dir + "1.png";
    const size_t len = 4096;
    wchar_t buffer[len] = { 0 };

    RecognitionSettings settings;
    set.auto_contrast = true;
    size_t result = asposeocr_page_settings(image.c_str(), buffer, len, settings);
#ifdef _WIN32
    setmode(_fileno(stdout), 0x00020000);
#else
    setlocale(LC_CTYPE, "");
#endif
    std::wcout << buffer;
```

## **Custom Image Correction Using Auto Denoising**
Aspose.OCR.Cpp provides the ability to remove noise to correct image quality.
For this, the API provides the [**RecognitionSettings.auto_denoising**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings) structure
to the [**page_settings()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga028cce64d935cf8fc8d5eab3d3713ebf) method.

The following code snippet demonstrates the use of the [**RecognitionSettings.auto_denoising**](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/)
property provides custom image quality correction. 

Note that automatic noise reduction is performed by a powerful neural network. It runs and corrects the image before recognition. 
It useful for images with noice, spots, flares, gradients, foreign elements.


## Sample Code

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	directory dir(".");
    const string current_dir = "";
    const string image = current_dir + "1.png";
    const size_t len = 4096;
    wchar_t buffer[len] = { 0 };

   RecognitionSettings settings;
    set.auto_denoising = true;
    size_t result = asposeocr_page_settings(image.c_str(), buffer, len, settings);
#ifdef _WIN32
    setmode(_fileno(stdout), 0x00020000);
#else
    setlocale(LC_CTYPE, "");
#endif
    std::wcout << buffer;
```

