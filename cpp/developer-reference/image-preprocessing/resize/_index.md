---
weight: 40
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
url: /cpp/resize/
feedback: OCRCPP
title: Resizing 
description: How to resize an image to improve recognition accuracy.
keywords:
- enlarge
- shrink
- width
- height
- upscale
- scale
---

The Aspose.OCR recognition engine can handle images of any size. However, very small and very large image sizes can adversely affect recognition:

- _Small images_ may lose some detail due to noise removal, binarization, and automatic contrast correction.
- Recognizing _very large images_ can take much more time and resources.

Aspose.OCR offers flexible preprocessing filters that allow you to upscale small images, shrink large images, or resize an image to predefined width and height.

## Proportional image scaling

To scale images up or down proportionally, use the `OCR_IMG_PREPROCESS_SCALE` preprocessing filter. The filter takes a scaling ratio (floating point number) as a parameter:

Scaling ratio | Result | Example
------------- | ------ | -------
`0` to `1`    | Shrink the image proportionally to the specified percentage. | `OCR_IMG_PREPROCESS_SCALE(0.3)` - proportionally reduce the width and height of the image down to 30%.
`1`           | Keep the original image size. | 
Above `1`     | Upscale the image proportionally to the specified percentage. | `OCR_IMG_PREPROCESS_SCALE(2)` - proportionally increase the width and height of the image to twice its original size.

```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_SCALE(0.8);
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
```

## Manual image resizing

You can manually define the width and height of the target image (in pixels) using the `OCR_IMG_PREPROCESS_RESIZE` preprocessing filter.

{{% alert color="primary" %}}
Applying this filter may cause the image to get out of proportion.
{{% /alert %}}

```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_RESIZE(1500, 2500);
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
```

## Usage scenarios 

- Medication guides.
- Food labels.
- Full-sized (raw) photos from high-resolution cameras and modern smartphones.
- Scanned images at very high (300+) DPI.
