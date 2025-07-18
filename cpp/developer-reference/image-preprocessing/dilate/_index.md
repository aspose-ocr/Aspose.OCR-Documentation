---
weight: 80
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/dilate/
feedback: OCRCPP
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

Some images, such as store receipts, have very thin characters that may be damaged by [automatic contrast corrections](/ocr/cpp/contrast/) or [binarization](/ocr/cpp/binarization/). 

Aspose.OCR provides a special preprocessing filter called _dilation_ that can increase the thickness of characters in an image by adding pixels to the edges of high-contrast objects, such as letters.

{{% alert color="primary" %}} 
Dilation automatically converts the image to [black and white](/ocr/cpp/binarization/#automatically-converting-the-image-to-black-and-white).
{{% /alert %}}

## Dilation

To increase the thickness of characters in an image, run the image through `OCR_IMG_PREPROCESS_DILATE` preprocessing filter.

```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_DILATE;
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
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

## Usage scenarios

Dilation is recommended for the following images:

- Receipts.
- Printouts with very thin font.
