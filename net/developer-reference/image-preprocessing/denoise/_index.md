---
weight: 20
date: "2022-08-10"
author: "Vladimir Lapin"
type: docs
url: /net/denoise/
title: Noise removal
description: How to remove dirt, spots, scratches, glare, and other image defects to improve recognition accuracy.
aliases:
- /net/denoising-correction/
keywords:
- denoise
- defect
- noise
- clean
- clear
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
		width: 569px;
		height: 376px;
		margin-bottom: 20px;
	}

	.duo > img {
		position: absolute;
	}
</style>

Dirt, spots, scratches, glare, unwanted gradients, and other noise are a common problem when scanning low-quality sources such as newspapers or old books, or when taking photographs. These image defects can interfere with recognition, significantly reduce the accuracy of OCR, and may cause spots to be misrecognised as characters.

Aspose.OCR provides automated processing algorithms that remove noise from images before proceeding to recognition.

## Automatic noise removal

To automatically remove the noise from the image before recognition, run the image through [`AutoDenoising`](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/autodenoising/) preprocessing filter or enable [`AutoDenoising`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/autodenoising/) property in recognition settings.

{{< tabs tabID="1" tabTotal="2" tabName1="Preprocessing filter" tabName2="Recognition settings" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add noise removal filter
Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter filters = new Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter();
filters.Add(Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter.AutoDenoising());
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
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Enable automatic noise removal in recognition settings
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AutoDenoising = true;
// Recognize image
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< /tabs >}}

<div class="duo">
	<img src="origin.png" alt="Noisy image" />
	<img src="result.png" alt="Denoised image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Remove noise</button>
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
			$(obj).text("Remove noise");
		}
	}
</script>

## Usage scenarios

Automatic noise removal is recommended for the following images:

- Photos, especially those taken in low light conditions.
- Old books.
- Newspapers.
- Postcards.
- Text with a photo or picture as a background.
- Scanned papers with spots and dirt.

However, noise removal can reduce recognition accuracy when working with poor-quality prints, as it can lead to the loss of important details, such as light punctuation or heavily fragmented characters.