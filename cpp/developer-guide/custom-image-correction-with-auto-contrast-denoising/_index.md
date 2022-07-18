---
title: Custom image preprocessing
type: docs
weight: 75
url: /cpp/custom-image-correction-with-auto-contrast-denoising/
---

Aspose.OCR for C++ automatically pre-processes images before recognition. However, some preprocessing operations are resource and time intensive and are therefore disabled by default. You can explicitly enable them to improve recognition results.

## Automatic contrast correction

This operation automatically improves the image contrast to the optimum level for recognition. To enable this preprocessing, create an instance of [RecognitionSettings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings) structure with `auto_contrast` property set to `true` and pass this instance to the [`page_settings`](https://reference.aspose.com/ocr/cpp/groupAspose#ga028cce64d935cf8fc8d5eab3d3713ebf) method.

### Example

The following code snippet demonstrates how to enable automatic contrast correction. Visit https://github.com/aspose-ocr/Aspose.OCR-for-C for the full project and sample data files.

```cpp
directory dir(".");
const string current_dir = "";
const string image = current_dir + "1.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };

RecognitionSettings settings;
// Enable automatic contrast correction
settings.auto_contrast = true;
// Recognize image with preprocessing
size_t result = asposeocr_page_settings(image.c_str(), buffer, len, settings);

#ifdef _WIN32
  setmode(_fileno(stdout), 0x00020000);
#else
  setlocale(LC_CTYPE, "");
#endif
  std::wcout << buffer;
```

## Automatic denoising

Dirt, spots, scratches, glare, unwanted gradients, and other image defects can interfere with recognition and significantly reduce OCR accuracy. Aspose.OCR for C++ provides a powerful Binarized Neural Network (BNN) that can clean up an image and reduce or completely remove noise.

To enable denoising, create an instance of [RecognitionSettings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings) structure with `auto_denoising` property set to `true` and pass this instance to the [`page_settings`](https://reference.aspose.com/ocr/cpp/groupAspose#ga028cce64d935cf8fc8d5eab3d3713ebf) method.

{{% alert color="primary" %}}

Automatic denoising requires additional processing resources and can reduce recognition speed on entry-level computers.

{{% /alert %}}

### Example

The following code snippet demonstrates how to enable automatic noise removal. Visit https://github.com/aspose-ocr/Aspose.OCR-for-C for the full project and sample data files.

```cpp
directory dir(".");
const string current_dir = "";
const string image = current_dir + "1.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };

RecognitionSettings settings;
// Enable automatic noise reduction
set.auto_denoising = true;
// Recognize image with preprocessing
size_t result = asposeocr_page_settings(image.c_str(), buffer, len, settings);

#ifdef _WIN32
  setmode(_fileno(stdout), 0x00020000);
#else
  setlocale(LC_CTYPE, "");
#endif
  std::wcout << buffer;
```
