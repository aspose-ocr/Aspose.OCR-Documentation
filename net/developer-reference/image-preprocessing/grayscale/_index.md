---
weight: 60
date: "2022-08-15"
author: "Vladimir Lapin"
type: docs
url: /net/grayscale/
title: Conversion to grayscale
description: How to convert source images to grayscale before recognition.
keywords:
- grayscale
- greyscale
- gray
- grey
- desaturate
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
		width: 500px;
		height: 322px;
		margin-bottom: 20px;
	}

	.duo > img {
		position: absolute;
	}
</style>

In most cases, color is not needed for recognition and can even mislead OCR algorithms. Grayscale allows images to be processed more efficiently, resulting in less specks, cleaner backgrounds, and crisper text than color images. Converting to grayscale can also improve the results of other preprocessing filters, such as automatic [deskewing](/ocr/net/deskew/).

Aspose.OCR provides a method for converting an image to grayscale before proceeding with preprocessing or OCR.

## Grayscale conversion

To convert the image to grayscale, run the image through [`ToGrayscale`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/tograyscale/) preprocessing filter.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Apply grayscale conversion filter
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.ToGrayscale());
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
	<img src="origin.png" alt="Color image" />
	<img src="result.png" alt="Grayscale image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Convert to grayscale</button>
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
			$(obj).text("Convert to grayscale");
		}
	}
</script>

## Usage scenarios

Grayscale conversion is recommended for the following images:

- Photos.
- Scanned ID cards and other personal documents.
- Full-color scans.

{{% alert color="primary" %}}
Improvements in recognition accuracy and preprocessing enhancements will be highly dependent on the original image and should be empirically tested.
{{% /alert %}}