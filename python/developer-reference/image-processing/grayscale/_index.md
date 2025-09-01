---
weight: 60
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/grayscale/
feedback: OCRPYNET
title: Conversion to grayscale
description: How to convert source images to grayscale using Aspose.OCR for Python via .NET before recognition.
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

In most cases, color is not needed for recognition and can even mislead OCR algorithms. Grayscale allows images to be processed more efficiently, resulting in less specks, cleaner backgrounds, and crisper text than color images. Converting to grayscale can also improve the results of other processing filters, such as automatic [deskewing](/ocr/python-net/deskew/).

Aspose.OCR for Python via .NET provides a method for converting an image to grayscale before proceeding with image processing or OCR.

{{% alert color="primary" %}}
Grayscale conversion is automatically performed when applying the [median filter](/ocr/python-net/median/).
{{% /alert %}}

## Grayscale conversion

To convert the image to grayscale, run the image through `to_grayscale` processing filter.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Initialize image processing
filters = PreprocessingFilter()
filters.add(PreprocessingFilter.to_grayscale())
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

In addition, grayscale conversion may decrease the original image size.

{{% alert color="primary" %}}
Improvements in recognition accuracy and quality enhancements will be highly dependent on the original image and should be empirically tested.
{{% /alert %}}
