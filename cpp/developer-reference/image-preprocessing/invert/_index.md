---
weight: 70
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/invert/
feedback: OCRCPP
title: Color inversion
description: How to swap colors in an image to improve recognition accuracy.
keywords:
- invert
- dark
- black
- white
- swap
- reverse
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

When working with white (or light) text on a black (or other dark) background, recognition accuracy may suffer. It can be greatly improved by reversing the colors of the image so that light areas appear dark and dark areas appear light. In addition, other colors are also swapped: red becomes cyan, green becomes magenta, blue becomes yellow, and so on.

Aspose.OCR provides the automated preprocessing filter that inverts colors in the image before proceeding to recognition.

## Inverting image colors

To automatically invert colors in an image before recognition, run the image through `OCR_IMG_PREPROCESS_INVERT` preprocessing filter.

```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_INVERT;
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
```

<div class="duo">
	<img src="origin.png" alt="White text on dark background" />
	<img src="result.png" alt="Inverted image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Invert colors</button>
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
			$(obj).text("Invert colors");
		}
	}
</script>

## Usage scenarios

Automatic color inversion is recommended for the following images:

- White text on black background.
- Advertisements.
- Business cards.
- Screenshots.
