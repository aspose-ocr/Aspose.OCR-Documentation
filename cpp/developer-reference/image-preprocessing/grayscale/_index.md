---
weight: 60
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
url: /cpp/grayscale/
feedback: OCRCPP
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

In most cases, color is not needed for recognition and can even mislead OCR algorithms. Grayscale allows images to be processed more efficiently, resulting in less specks, cleaner backgrounds, and crisper text than color images. Converting to grayscale can also improve the results of other preprocessing filters, such as automatic [deskewing](/ocr/cpp/deskew/).

Aspose.OCR provides a function for converting an image to grayscale before proceeding with preprocessing or OCR.

{{% alert color="primary" %}}
Grayscale conversion is automatically performed when applying the [median filter](/ocr/cpp/median/).
{{% /alert %}}

## Grayscale conversion

To convert the image to grayscale, run the image through `OCR_IMG_PREPROCESS_GRAYSCALE` preprocessing filter.

```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_GRAYSCALE;
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
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
