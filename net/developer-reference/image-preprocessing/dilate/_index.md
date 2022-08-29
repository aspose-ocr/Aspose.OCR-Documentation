---
weight: 80
date: "2022-08-26"
author: "Vladimir Lapin"
type: docs
url: /net/dilate/
title: Dilation
description: How to make characters in an image thicker to improve recognition accuracy.
keywords:
- dilate
- thick
- strong
- crisp
---

<style>
	button {
		cursor: pointer;
		margin-right: 20px;
		padding: 7px 15px;
		border: none;
		border-radius: 5px;
		background-color: #1a89d0;
		font-weight: 700;
		font-size: 15px;
		color: #ffffff;
	}

	button:hover {
		background-color: #3071a9;
	}

	button:focus {
		outline: none;
	}

	.duo {
		position: relative;
		width: 600px;
		height: 300px;
		margin-bottom: 20px;
	}

	.duo > img {
		position: absolute;
	}
</style>

Some images, such as store receipts, have very thin characters that may be damaged by [automatic contrast corrections](/ocr/net/contrast/) or [binarization](/ocr/net/binarization/). 

Aspose.OCR provides a special preprocessing filter called _dilation_ that can increase the thickness of characters in an image by adding pixels to the edges of high-contrast objects, such as letters.

{{% alert color="primary" %}} 
Dilation automatically converts the image to [black and white](/ocr/net/binarization/#automatically-converting-the-image-to-black-and-white).
{{% /alert %}}

## Dilation

To increase the thickness of characters in an image, run the image through [`Dilate`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/dilate/) preprocessing filter.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Apply dilate filter
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Dilate());
// Save preprocessed image to file for debugging purposes
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

<div class="duo">
	<img src="origin.png" alt="Ultra-light font" />
	<img src="result.png" alt="Strong font" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Make text thicker</button>
<script>
	function triggerSkew(obj)
	{
		let images = $(".duo > img");
		let skewed = images.eq(0).is(":visible");
		if(skewed)
		{
			images.eq(1).show(200);
			images.eq(0).hide(200);
			$(obj).text("Revert to original image");
		}
		else
		{
			images.eq(0).show(200);
			images.eq(1).hide(200);
			$(obj).text("Make text thicker");
		}
	}
</script>

## Image regions preprocessing

`Dilate` filter can be applied to specific regions of an image. For example, you can make the article body text thicker while leaving the headers unchanged.

To apply a filter to an area, specify its top left corner along with width and height as [`Aspose.Drawing.Rectangle`](https://reference.aspose.com/drawing/net/system.drawing/rectangle/) object. If the region is omitted, the filter is applied to the entire image.

```csharp
Aspose.Drawing.Rectangle rectangle = new Aspose.Drawing.Rectangle(5, 161, 340, 113);
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.Dilate(rectangle));
```

## Usage scenarios

Dilation is recommended for the following images:

- Receipts.
- Printouts with very thin font.
