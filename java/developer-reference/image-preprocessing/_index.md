---
weight: 10
date: "2022-09-24"
author: "Vladimir Lapin"
type: docs
url: /java/image-preprocessing/
feedback: OCRJAVA
title: Image preprocessing
description: Automatic or manual actions for formatting an image before sending it for recognition.
aliases:
- /java/custom-image-correction-with-preprocessing-filters/
keywords:
- preprocess
- correct
- fix
- adjust
---

<style>
	#filters-chain > div {
		display: flex;
		align-items: center;
	}

	#filters-chain > div > label {
		margin: 0 0 0 7px;
		font-weight: 700;
	}

	.hidden {
		display: none !important;
	}
</style>

The accuracy and reliability of text recognition is highly dependent on the quality of the original image. Aspose.OCR offers a large number of fully automated and manual image processing filters that enhance an image before it is sent to the OCR engine.

Each preprocessing filter increases the image processing time. The approximate amount of additional time required for pre-processing (as a percentage of the minimum image processing pipeline) is listed in the **Performance Impact** column.

Filter | Action | Performance impact | Usage scenarios
------ | ------ | ------------------ | ---------------
[Skew correction](/ocr/java/deskew/#automatic-skew-correction) | Automatically straighten images aligned at a slight angle to the horizontal. | 12% | Skewed images
[Rotation](/ocr/java/deskew/#manual-skew-correction) | Manually rotate severely skewed images. | 7.5% | Rotated images
[Noise removal](/ocr/java/denoise/) | Automatically remove dirt, spots, scratches, glare, unwanted gradients, and other noise from photos and scans. | 175% extra time<br />38% more memory <sup>(1)</sup> | Photos<br />Old books<br />Newspapers<br />Postcards<br />Documents with stains and dirt
[Contrast correction](/ocr/java/contrast/) | Automatically adjust the image contrast. | 7.5% | Photos<br />Old papers<br />Text on a background
[Resizing](/ocr/java/resize/) | Proportionally scale images up / down, or manually define the width and height of the image. | up to 100% <sup>(2)</sup> | Medication guides<br />Food labels<br />Full-sized photos from modern cameras and smartphones<br />Scanned images at very high DPI
[Binarization](/ocr/java/binarization/) | Convert images to black and white automatically or manually adjust the criteria that determines whether a pixel is considered black or white. | 0.9% |  Always used for text detection and most automatic image corrections
[Conversion to grayscale](/ocr/java/grayscale/) | Discard color information from images and leave only shades of gray. | 0.5% | Photos<br />Scanned ID cards<br />Full-color scans
[Color inversion](/ocr/java/invert/) | Swap image colors so that light areas appear dark and dark areas appear light. | 0.25% | White text on black background<br />Advertisements<br />Business cards<br />Screenshots
[Dilation](/ocr/java/dilate/) | Increase the thickness of characters in an image by adding pixels to the edges of high-contrast objects, such as letters. | 3.1% | Receipts<br />Printouts with very thin font
[Median filter](/ocr/java/median/) | Blur noisy images while preserving the edges of high-contrast objects like letters. | 6.25% | Photos taken in low light conditions<br />Poor quality printouts<br />Highly compressed JPEG’s

{{% alert color="primary" %}}
**Notes**

1. Automatic noise removal uses a powerful artificial intelligence algorithm that consumes significant computing resources and RAM. Use it with care, especially when developing public websites and mobile apps.
2. Resizing takes between 6% and 100% more time than the minimum processing pipeline, depending on the original image size.
{{% /alert %}}

## Chaining preprocessing filters

Multiple preprocessing filters can be applied to the same image to further improve the recognition quality. The filters are applied one by one in the order they are added to [`PreprocessingFilter`](https://reference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter) object.

Note that each filter requires additional time and resources on the computer running the application. Do not add extra filters if you are satisfied with the recognition accuracy, especially when developing web applications.

<div id="filters-chain">
	<div>
		<input type="checkbox" id="threshold" impact="0.9" />
		<label for="threshold">Set binarization threshold</label>
	</div>
	<div>
		<input type="checkbox" id="deskew" impact="12" />
		<label for="deskew">Correct skew</label>
	</div>
	<div>
		<input type="checkbox" id="rotate" impact="7.5" />
		<label for="rotate">Rotate</label>
	</div>
	<div>
		<input type="checkbox" id="denoise" impact="175" />
		<label for="denoise">Remove noise</label>
	</div>
	<div>
		<input type="checkbox" id="contrast" impact="7.5" />
		<label for="contrast">Adjust contrast</label>
	</div>
	<div>
		<input type="checkbox" id="scale" impact="6" />
		<label for="scale">Scale</label>
	</div>
	<div>
		<input type="checkbox" id="resize" impact="6" />
		<label for="resize">Resize</label>
	</div>
	<div>
		<input type="checkbox" id="grayscale" impact="0.5" />
		<label for="grayscale">Convert to grayscale</label>
	</div>
	<div>
		<input type="checkbox" id="invert" impact="0.25" />
		<label for="invert">Invert colors</label>
	</div>
	<div>
		<input type="checkbox" id="dilate" impact="3.1" />
		<label for="dilate">Dilate</label>
	</div>
	<div>
		<input type="checkbox" id="median" impact="6.25" />
		<label for="median">Apply median filter</label>
	</div>
</div>

<div class="highlight" id="filters-code"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-java" data-lang="java"><span style="display:flex;"><span><span style="color:#000">PreprocessingFilter</span> <span style="color:#000">filters</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#204a87;font-weight:bold">new</span> <span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">();</span>
</span></span><span style="display:flex;" id="threshold-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Threshold</span><span style="color:#ce5c00;font-weight:bold">({</span><span style="color:#000">THRESHOLD</span><span style="color:#ce5c00;font-weight:bold">}));</span>
</span></span><span style="display:flex;" id="deskew-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">AutoSkew</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span><span style="display:flex;" id="rotate-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Rotate</span><span style="color:#ce5c00;font-weight:bold">({</span><span style="color:#000">ANGLE</span><span style="color:#ce5c00;font-weight:bold">}));</span>
</span></span><span style="display:flex;" id="denoise-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">AutoDenoising</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span><span style="display:flex;" id="contrast-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">ContrastCorrectionFilter</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span><span style="display:flex;" id="scale-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Scale</span><span style="color:#ce5c00;font-weight:bold">({</span><span style="color:#000">RATIO</span><span style="color:#ce5c00;font-weight:bold">}));</span>
</span></span><span style="display:flex;" id="resize-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Resize</span><span style="color:#ce5c00;font-weight:bold">({</span><span style="color:#000">WIDTH</span><span style="color:#ce5c00;font-weight:bold">},</span> <span style="color:#ce5c00;font-weight:bold">{</span><span style="color:#000">HEIGHT</span><span style="color:#ce5c00;font-weight:bold">}));</span>
</span></span><span style="display:flex;" id="grayscale-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">ToGrayscale</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span><span style="display:flex;" id="invert-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Invert</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span><span style="display:flex;" id="dilate-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Dilate</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span><span style="display:flex;" id="median-code" class="hidden"><span><span style="color:#000">filters</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">add</span><span style="color:#ce5c00;font-weight:bold">(</span><span style="color:#000">PreprocessingFilter</span><span style="color:#ce5c00;font-weight:bold">.</span><span style="color:#c4a000">Median</span><span style="color:#ce5c00;font-weight:bold">());</span>
</span></span></code></pre></div>

**Approximate increase of processing time: <span id="impact-time">0</span>%**

## Image regions preprocessing

Most preprocessing filters can be applied to specific regions of an image. For example, you can invert a newspaper headline written in white on black, leaving the rest of the article unchanged.

Multiple preprocessing filters can be applied to different regions of the same image. If the regions intersect each other, filters are applied to the intersection in their [chaining](#chaining-preprocessing-filters) order in [`PreprocessingFilter`](https://reference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter) object.

![Applying preprocessing to intersecting regions](filter-region.png)

To apply a filter to an area, specify its top left corner along with width and height as [`Rectangle`](https://docs.oracle.com/javase/8/docs/api/java/awt/Rectangle.html) object. If the region is omitted, the filter is applied to the entire image.

```java
AsposeOCR api = new AsposeOCR();
// Define image regions
Rectangle blackRectangle = new Rectangle(5, 161, 340, 113);
PreprocessingFilter filters = new PreprocessingFilter();
// (1) Invert black region
filters.add(PreprocessingFilter.Invert(blackRectangle));
// (2) Denoise entire image
filters.add(PreprocessingFilter.AutoDenoising());
// Save preprocessed image to file
BufferedImage imageRes = api.PreprocessImage("source.png", filters);
File outputSource = new File("result.png");
ImageIO.write(imageRes, "png", outputSource);
```

The following filters can be applied to regions:

- [Skew correction](/ocr/java/deskew/#image-regions-preprocessing)
- [Noise removal](/ocr/java/denoise/#image-regions-preprocessing)
- [Contrast correction](/ocr/java/contrast/#image-regions-preprocessing)
- [Binarization](/ocr/java/binarization/#image-regions-preprocessing)
- [Color inversion](/ocr/java/invert/#image-regions-preprocessing)
- [Dilation](/ocr/java/dilate/#image-regions-preprocessing)
- [Median filter](/ocr/java/median/#image-regions-preprocessing)

## Viewing preprocessed images

Aspose.OCR offers an easy way to access or save preprocessed images using `PreprocessImage` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. This method returns a [`BufferedImage`](https://docs.oracle.com/javase/8/docs/api/java/awt/image/BufferedImage.html) object that can be sent for recognition or saved to a file.

You can use this file to analyze the effectiveness of preprocessing filters, exclude unnecessary filters that consume resources without affecting the result, or show the result of preprocessing in the user interface.

```java
AsposeOCR api = new AsposeOCR();
// Add noise removal filter
PreprocessingFilter filters = new PreprocessingFilter();
filters.add(PreprocessingFilter.AutoDenoising());
// Save preprocessed image to file
BufferedImage imageRes = api.PreprocessImage("source.png", filters);
File outputSource = new File("result.png");
ImageIO.write(imageRes, "png", outputSource);
```

<script>
window.addEventListener("load", function(){
	$("#filters-chain input").change(applyFilter);
});

function applyFilter()
{
	let status = $(this).prop("checked");
	switch($(this).attr("id"))
	{
		case "threshold":
			if(status) $("#threshold-code").removeClass("hidden");
			else $("#threshold-code").addClass("hidden");
			break;
		case "deskew":
			if(status) $("#deskew-code").removeClass("hidden");
			else $("#deskew-code").addClass("hidden");
			if(status)
			{
				$("#rotate").prop("checked", false);
				$("#rotate-code").addClass("hidden");
			}
			break;
		case "rotate":
			if(status) $("#rotate-code").removeClass("hidden");
			else $("#rotate-code").addClass("hidden");
			if(status)
			{
				$("#deskew").prop("checked", false);
				$("#deskew-code").addClass("hidden");
			}
			break;
		case "denoise":
			if(status) $("#denoise-code").removeClass("hidden");
			else $("#denoise-code").addClass("hidden");
			break;
		case "contrast":
			if(status) $("#contrast-code").removeClass("hidden");
			else $("#contrast-code").addClass("hidden");
			break;
		case "scale":
			if(status) $("#scale-code").removeClass("hidden");
			else $("#scale-code").addClass("hidden");
			if(status)
			{
				$("#resize").prop("checked", false);
				$("#resize-code").addClass("hidden");
			}
			break;
		case "resize":
			if(status) $("#resize-code").removeClass("hidden");
			else $("#resize-code").addClass("hidden");
			if(status)
			{
				$("#scale").prop("checked", false);
				$("#scale-code").addClass("hidden");
			}
			break;
		case "grayscale":
			if(status) $("#grayscale-code").removeClass("hidden");
			else $("#grayscale-code").addClass("hidden");
			break;
		case "invert":
			if(status) $("#invert-code").removeClass("hidden");
			else $("#invert-code").addClass("hidden");
			break;
		case "dilate":
			if(status) $("#dilate-code").removeClass("hidden");
			else $("#dilate-code").addClass("hidden");
			break;
		case "median":
			if(status) $("#median-code").removeClass("hidden");
			else $("#median-code").addClass("hidden");
			if(status)
			{
				$("#grayscale").prop("checked", false);
				$("#grayscale-code").addClass("hidden");
			}
			break;
		default:
			break;
	}
	let total=0;
	$("#filters-chain input").each(function(){
		let box = $(this);
		if(box.prop("checked")) total += parseFloat(box.attr("impact"));
	});
	$("#impact-time").text(total);
}
</script>