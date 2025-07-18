---
weight: 20
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/denoise/
feedback: OCRPYNET
title: Noise removal
description: How to remove dirt, spots, scratches, glare, and other image defects using Aspose.OCR for Python via .NET to improve recognition accuracy.
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

Aspose.OCR for Python via .NET provides automated processing algorithms that remove noise from images before proceeding to recognition.

{{% alert color="primary" %}} 
Noise removal automatically converts the image to [black and white](/ocr/python-net/binarization/#automatically-converting-the-image-to-black-and-white).
{{% /alert %}}

## Automatic noise removal

To automatically remove the noise from the image before recognition, run the image through `auto_denoising` processing filter.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.auto_denoising())
# Add image to the recognition batch and apply processing filter
input = OcrInput(InputType.SINGLE_IMAGE, filters)
input.add("source.png")
# Save processed image to the "result" folder
ImageProcessing.save(input, "result")
# Recognize the image
result = api.recognize(input)
# Print recognition result
print(result[0].recognition_text)
```

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
