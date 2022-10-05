---
weight: 70
date: "2022-09-24"
author: "Vladimir Lapin"
type: docs
url: /java/invert/
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

To automatically invert colors in an image before recognition, run the image through [`Invert`](https://reference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter#Invert--) preprocessing filter.

```java
AsposeOCR api = new AsposeOCR();
// Scale the image to twice its original size using bilinear interpolation
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.Invert());
// Save preprocessed image to file
BufferedImage imageRes = api.PreprocessImage("source.png", filters);
File outputSource = new File("result.png");
ImageIO.write(imageRes, "png", outputSource);
// Append preprocessing filters to recognition settings
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setPreprocessingFilters(filters);
// Recognize image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
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

## Image regions preprocessing

You can invert certain areas of the image, such as black on a white headers, while leaving the rest of the content unchanged.

To apply a filter to an area, specify its top left corner along with width and height as [`Rectangle`](https://docs.oracle.com/javase/8/docs/api/java/awt/Rectangle.html) object. If the region is omitted, the filter is applied to the entire image.

```java
Rectangle rectangle = new Rectangle(5, 161, 340, 340);
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.Invert(rectangle));
```

## Usage scenarios

Automatic color inversion is recommended for the following images:

- White text on black background.
- Advertisements.
- Business cards.
- Screenshots.
