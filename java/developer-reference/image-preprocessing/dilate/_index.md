---
weight: 80
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
url: /java/dilate/
feedback: OCRJAVA
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

Some images, such as store receipts, have very thin characters that may be damaged by [automatic contrast corrections](/ocr/java/contrast/) or [binarization](/ocr/java/binarization/). 

Aspose.OCR provides a special preprocessing filter called _dilation_ that can increase the thickness of characters in an image by adding pixels to the edges of high-contrast objects, such as letters.

{{% alert color="primary" %}} 
Dilation automatically converts the image to [black and white](/ocr/java/binarization/#automatically-converting-the-image-to-black-and-white).
{{% /alert %}}

## Dilation

To increase the thickness of characters in an image, run the image through [`BinarizeAndDilate`](https://reference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter#BinarizeAndDilate--) preprocessing filter.

```java
AsposeOCR api = new AsposeOCR();
// Make text thicker
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.BinarizeAndDilate());
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage, filters);
images.add("image.png");
// Save processed images to the folder
ImageProcessing.Save(images, "C:\\images");
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

`BinarizeAndDilate` filter can be applied to specific regions of an image. For example, you can make the article body text thicker while leaving the headers unchanged.

To apply a filter to an area, specify its top left corner along with width and height as [`Rectangle`](https://docs.oracle.com/javase/8/docs/api/java/awt/Rectangle.html) object. If the region is omitted, the filter is applied to the entire image.

```java
Rectangle rectangle = new Rectangle(5, 161, 340, 340);
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.BinarizeAndDilate(rectangle));
```

## Usage scenarios

Dilation is recommended for the following images:

- Receipts.
- Printouts with very thin font.
