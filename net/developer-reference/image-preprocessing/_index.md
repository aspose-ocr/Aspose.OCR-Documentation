---
weight: 30
date: "2022-08-18"
author: "Vladimir Lapin"
type: docs
url: /net/image-preprocessing/
title: Image preprocessing
description: Automatic or manual actions for formatting an image before sending it for recognition.
aliases:
- /net/custom-image-correction-with-preprocessing-filters/
keywords:
- preprocess
- correct
- fix
- adjust
---

The accuracy and reliability of text recognition is highly dependent on the quality of the original image. Aspose.OCR offers a large number of fully automated and manual image processing filters that enhance an image before it is sent to the OCR engine.

Filter | Action | Usage scenarios
------ | ------ | ---------------
[Skew correction](/ocr/net/deskew/) | Automatically straighten images aligned at a slight angle to the horizontal, or manually rotate severely skewed images. | Skewed images
[Noise removal](/ocr/net/denoise/) | Automatically remove dirt, spots, scratches, glare, unwanted gradients, and other noise from photos and scans. | Photos<br />Old books<br />Newspapers<br />Postcards<br />Documents with stains and dirt
[Contrast correction](/ocr/net/contrast/) | Automatically adjust the image contrast. | Photos<br />Old papers<br />Text on a background
[Resizing](/ocr/net/resize/) | Proportionally scale images up / down, or manually define the width and height of the image. | Medication guides<br />Food labels<br />Full-sized photos<br />Scanned images at very high DPI
[Binarization](/ocr/net/binarization/) | Convert images to black and white automatically or manually adjust the criteria that determines whether a pixel is considered black or white. | Always used for text detection and most automatic image corrections
[Conversion to grayscale](/ocr/net/grayscale/) | Discard color information from images and leave only shades of gray. | Photos<br />Scanned ID cards<br />Full-color scans
[Color inversion](/ocr/net/invert/) | Swap image colors so that light areas appear dark and dark areas appear light. | White text on black background<br />Advertisements<br />Business cards<br />Screenshots
[Dilation](/ocr/net/dilate/) | Increase the thickness of characters in an image by adding pixels to the edges of high-contrast objects, such as letters. | Receipts<br />Printouts with very thin font
[Median filter](/ocr/net/median/) | Blur noisy images while preserving the edges of high-contrast objects like letters. | Photos taken in low light conditions<br />Poor quality printouts<br />Highly compressed JPEG’s

## Chaining preprocessing filters

Multiple preprocessing filters can be applied to the same image to further improve the recognition quality. The filters are applied one by one in the order they are added to [`PreprocessingFilter`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) object.

```csharp
// Invert colors -> Remove noise -> Automatically straighten an image
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Invert());
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.AutoDenoising());
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.AutoSkew());
```

Note that each filter requires additional time and resources on the computer running the application. Do not add extra filters if you are satisfied with the recognition accuracy, especially when developing web applications.

## Viewing preprocessed images

Aspose.OCR offers an easy way to access or save preprocessed images using [`PreprocessImage`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/preprocessimage/) method of `Aspose.OCR.AsposeOcr` class. This method returns a memory stream that can be sent for recognition or saved to a file.

You can use this file to analyze the effectiveness of preprocessing filters, exclude unnecessary filters that consume resources without affecting the result, or show the result of preprocessing in the user interface.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add noise removal filter
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.AutoDenoising());
// Save preprocessed image to file
using(MemoryStream ms = recognitionEngine.PreprocessImage("source.png", filters))
{
	using(FileStream fs = new FileStream("result.png", FileMode.Create, FileAccess.Write))
	{
		ms.WriteTo(fs);
	}
}
```
