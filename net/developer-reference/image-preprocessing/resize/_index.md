---
weight: 40
date: "2022-08-11"
author: "Vladimir Lapin"
type: docs
url: /net/resize/
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

Aspose.OCR offers flexible preprocessing filters that allow you to upscale small images, shrink large images, or resize an image to predefined width and height.

## Proportional image scaling

To scale images up or down proportionally, use the [`Scale`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/scale/) preprocessing filter. The filter takes a scaling ratio (floating point number) as a parameter:

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
// Save resized image to file for debugging purposes
using(MemoryStream ms = recognitionEngine.PreprocessImage("source.png", filters))
{
	using(FileStream fs = new FileStream("result.png", FileMode.Create, FileAccess.Write))
	{
		ms.WriteTo(fs);
	}
}
// Append preprocessing filters to recognition settings
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.PreprocessingFilters = filters;
// Recognize image
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```

## Manual image resizing

You can manually define the width and height of the target image (in pixels) using the [`Resize`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/resize/) preprocessing filter. It also allows you to select an [interpolation algorithm](https://reference.aspose.com/ocr/net/aspose.ocr.filters/interpolationfiltertype/) as an optional parameter.

{{% alert color="primary" %}}
Applying this filter may cause the image to get out of proportion.
{{% /alert %}}

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Resize the image to 1000x1000 pixels with bilinear interpolation
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Resize(1000, 1000, Aspose.OCR.Filters.InterpolationFilterType.Triangle));
// Save resized image to file for debugging purposes
using(MemoryStream ms = recognitionEngine.PreprocessImage("source.png", filters))
{
	using(FileStream fs = new FileStream("result.png", FileMode.Create, FileAccess.Write))
	{
		ms.WriteTo(fs);
	}
}
// Append preprocessing filters to recognition settings
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.PreprocessingFilters = filters;
// Recognize image
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```

## Usage scenarios 

- Medication guides.
- Food labels.
- Full-sized (raw) photos from high-resolution cameras and modern smartphones.
- Scanned images at very high (300+) DPI.
