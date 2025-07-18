---
weight: 90
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/median/
feedback: OCRPYNET
title: Median filter
description: How to smooth out noise in an image using Aspose.OCR for Python via .NET before applying other processing filters or performing OCR.
keywords:
- gaussian
- blur
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

Photos taken in low light conditions can have a lot of digital noise. Noise can also show up in highly compressed JPEG images in form of compression artifacts. This noise can mislead OCR algorithms and prevent other processing filters from working properly.

Aspose.OCR for Python via .NET provides an alternative method for [removing noise](/ocr/python-net/denoise/) from an image at the cost of some detail, called the _median filter_. This makes the image a little blurry while preserving the edges of high-contrast objects such as letters. The results can be further improved with the [auto-contrast](/ocr/python-net/contrast/) or [binarization](/ocr/python-net/binarization/) processing filters.

{{% alert color="primary" %}} 
The median filter automatically converts the image to [grayscale](/ocr/python-net/grayscale/).
{{% /alert %}}

## Applying the median filter

To smooth out noise in an image, run the image through `median` processing filter.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.median())
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
	<img src="result.png" alt="Smooth noise" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Smooth noise</button>
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
			$(obj).text("Smooth noise");
		}
	}
</script>

## Usage scenarios

Median filter is recommended for the following images:

- Photos that were taken in low light conditions.
- Poor quality printouts.
- Highly compressed / low quality JPEG's.

{{% alert color="primary" %}}
Improvements in recognition accuracy will be highly dependent on the original image and should be empirically tested. Applying a median filter can sometimes result in the loss of important details such as very thin characters and punctuation.
{{% /alert %}}
