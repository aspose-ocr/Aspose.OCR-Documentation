---
weight: 40
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/resize/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
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

Aspose.OCR offers flexible processing filters that allow you to upscale small images, shrink large images, or resize an image to predefined width and height.

## Proportional image scaling

To scale images up or down proportionally, use the [`Scale`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/scale/) processing filter. The filter takes a scaling ratio (floating point number) as a parameter:

Scaling ratio | Result | Example
------------- | ------ | -------
`0` to `1`    | Shrink the image proportionally to the specified percentage. | `Scale(0.3F)` - proportionally reduce the width and height of the image down to 30%.
`1`           | Keep the original image size. | 
Above `1`     | Upscale the image proportionally to the specified percentage. | `Scale(2)` - proportionally increase the width and height of the image to twice its original size.

`Scale` filter also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/net/aspose.ocr.filters/interpolationfiltertype/) as an optional parameter.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Scale the image to twice its original size using bilinear interpolation
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Scale(2, Aspose.OCR.Filters.InterpolationFilterType.Triangle));
// Add an image to OcrInput object and apply processing filters
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage, filters);
input.Add("source.png");
// Save processed image to the folder
Aspose.OCR.ImageProcessing.Save(input, @"C:\result");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Manual image resizing

You can manually define the width and height of the target image (in pixels) using the [`Resize`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/resize/) processing filter. It also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/net/aspose.ocr.filters/interpolationfiltertype/) as an optional parameter.

{{% alert color="primary" %}}
Applying this filter may cause the image to get out of proportion.
{{% /alert %}}

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Resize the image to 1000x1000 pixels with bilinear interpolation
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Resize(1000, 1000, Aspose.OCR.Filters.InterpolationFilterType.Triangle));
// Add an image to OcrInput object and apply processing filters
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage, filters);
input.Add("source.png");
// Save processed image to the folder
Aspose.OCR.ImageProcessing.Save(input, @"C:\result");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Usage scenarios 

- Medication guides.
- Food labels.
- Full-sized (raw) photos from high-resolution cameras and modern smartphones.
- Scanned images at very high (300+) DPI.
