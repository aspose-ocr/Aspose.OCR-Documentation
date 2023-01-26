---
weight: 40
date: "2022-09-24"
author: "Vladimir Lapin"
type: docs
url: /java/resize/
feedback: OCRJAVA
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

To scale images up or down proportionally, use the [`Scale`](https://reference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter#Scale-float-) preprocessing filter. The filter takes a scaling ratio (floating point number) as a parameter:

Scaling ratio | Result | Example
------------- | ------ | -------
`0` to `1`    | Shrink the image proportionally to the specified percentage. | `Scale(0.3F)` - proportionally reduce the width and height of the image down to 30%.
`1`           | Keep the original image size. | 
Above `1`     | Upscale the image proportionally to the specified percentage. | `Scale(2)` - proportionally increase the width and height of the image to twice its original size.

`Scale` filter also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/java/com.aspose.ocr/InterpolationFilterType) as an optional parameter.

```java
AsposeOCR api = new AsposeOCR();
// Scale the image to twice its original size using bilinear interpolation
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.Scale(2, Aspose.OCR.Filters.InterpolationFilterType.Triangle));
// Save preprocessed image to file
BufferedImage imageRes = api.PreprocessImage("source.png", filters);
File outputSource = new File("result.png");
ImageIO.write(imageRes, "png", outputSource);
// Append preprocessing filters to recognition settings
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setPreprocessingFilters(filters);
// Recognize image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```

## Manual image resizing

You can manually define the width and height of the target image (in pixels) using the [`Resize`](https://reference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter#Resize-int-int-) preprocessing filter. It also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/java/com.aspose.ocr/InterpolationFilterType) as an optional parameter.

{{% alert color="primary" %}}
Applying this filter may cause the image to get out of proportion.
{{% /alert %}}

```java
AsposeOCR api = new AsposeOCR();
// Resize the image to 1000x1000 pixels with bilinear interpolation
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.Resize(1000, 1000, InterpolationFilterType.Triangle));
// Save preprocessed image to file
BufferedImage imageRes = api.PreprocessImage("source.png", filters);
File outputSource = new File("result.png");
ImageIO.write(imageRes, "png", outputSource);
// Append preprocessing filters to recognition settings
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setPreprocessingFilters(filters);
// Recognize image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```

## Usage scenarios 

- Medication guides.
- Food labels.
- Full-sized (raw) photos from high-resolution cameras and modern smartphones.
- Scanned images at very high (300+) DPI.
