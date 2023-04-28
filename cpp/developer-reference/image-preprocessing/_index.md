---
weight: 15
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
url: /cpp/image-preprocessing/
feedback: OCRCPP
title: Image preprocessing
description: Automatic or manual actions for formatting an image before sending it for recognition.
aliases:
- /cpp/custom-image-correction-with-preprocessing-filters/
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
[Skew correction](/ocr/cpp/deskew/#automatic-skew-correction) | Automatically straighten images aligned at a slight angle to the horizontal. | 12% | Skewed images
[Rotation](/ocr/cpp/deskew/#manual-skew-correction) | Manually rotate severely skewed images. | 7.5% | Rotated images
[Noise removal](/ocr/cpp/denoise/) | Automatically remove dirt, spots, scratches, glare, unwanted gradients, and other noise from photos and scans. | 175% extra time<br />38% more memory <sup>(1)</sup> | Photos<br />Old books<br />Newspapers<br />Postcards<br />Documents with stains and dirt
[Contrast correction](/ocr/cpp/contrast/) | Automatically adjust the image contrast. | 7.5% | Photos<br />Old papers<br />Text on a background
[Resizing](/ocr/cpp/resize/) | Proportionally scale images up / down, or manually define the width and height of the image. | up to 100% <sup>(2)</sup> | Medication guides<br />Food labels<br />Full-sized photos from modern cameras and smartphones<br />Scanned images at very high DPI
[Binarization](/ocr/cpp/binarization/) | Convert images to black and white automatically or manually adjust the criteria that determines whether a pixel is considered black or white. | 0.9% |  Always used for text detection and most automatic image corrections
[Conversion to grayscale](/ocr/cpp/grayscale/) | Discard color information from images and leave only shades of gray. | 0.5% | Photos<br />Scanned ID cards<br />Full-color scans
[Color inversion](/ocr/cpp/invert/) | Swap image colors so that light areas appear dark and dark areas appear light. | 0.25% | White text on black background<br />Advertisements<br />Business cards<br />Screenshots
[Dilation](/ocr/cpp/dilate/) | Increase the thickness of characters in an image by adding pixels to the edges of high-contrast objects, such as letters. | 3.1% | Receipts<br />Printouts with very thin font
[Median filter](/ocr/cpp/median/) | Blur noisy images while preserving the edges of high-contrast objects like letters. | 6.25% | Photos taken in low light conditions<br />Poor quality printouts<br />Highly compressed JPEG’s

{{% alert color="primary" %}}
**Notes**

1. Automatic noise removal uses a powerful artificial intelligence algorithm that consumes significant computing resources and RAM. Use it with care, especially when developing public websites and mobile apps.
2. Resizing takes between 6% and 100% more time than the minimum processing pipeline, depending on the original image size.
{{% /alert %}}

## Chaining preprocessing filters

Multiple preprocessing filters can be applied to the same image to further improve the recognition quality. The filters are applied one by one in the order they are added to `custom_preprocessing_filters` structure.

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

<div class="highlight"><pre tabindex="0" style="background-color:#f8f8f8;-moz-tab-size:4;-o-tab-size:4;tab-size:4;"><code class="language-cpp" data-lang="cpp"><span style="display:flex;"><span><span style="color:#000">custom_preprocessing_filters</span> <span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="threshold-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_1</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_THRESHOLD</span><span style="color:#000;font-weight:bold">({</span><span style="color:#000">THRESHOLD</span><span style="color:#000;font-weight:bold">});</span>
</span></span><span style="display:flex;" id="deskew-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_2</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_AUTOSKEW</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="rotate-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_3</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_ROTATE</span><span style="color:#000;font-weight:bold">({</span><span style="color:#000">ANGLE</span><span style="color:#000;font-weight:bold">});</span>
</span></span><span style="display:flex;" id="denoise-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_4</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_AUTODENOISING</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="contrast-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_5</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_CONTRAST_CORRECTION</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="scale-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_6</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_SCALE</span><span style="color:#000;font-weight:bold">({</span><span style="color:#000">RATIO</span><span style="color:#000;font-weight:bold">});</span>
</span></span><span style="display:flex;" id="resize-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_7</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_RESIZE</span><span style="color:#000;font-weight:bold">({</span><span style="color:#000">WIDTH</span><span style="color:#000;font-weight:bold">},</span> <span style="color:#000;font-weight:bold">{</span><span style="color:#000">HEIGHT</span><span style="color:#000;font-weight:bold">});</span>
</span></span><span style="display:flex;" id="grayscale-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_8</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_GRAYSCALE</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="invert-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_9</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_INVERT</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="dilate-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_10</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_DILATE</span><span style="color:#000;font-weight:bold">;</span>
</span></span><span style="display:flex;" id="median-code" class="hidden"><span><span style="color:#000">filters_</span><span style="color:#000;font-weight:bold">.</span><span style="color:#000">filter_11</span> <span style="color:#ce5c00;font-weight:bold">=</span> <span style="color:#000">OCR_IMG_PREPROCESS_MEDIAN</span><span style="color:#000;font-weight:bold">;</span>
</span></span></code></pre></div>

**Approximate increase of processing time: <span id="impact-time">0</span>%**

## Viewing preprocessed images

Aspose.OCR for C++ offers an easy way to save preprocessed images using [`preprocess_page_and_save()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga69cc8aa64a4cd77628f3b273c3d41645) or [`preprocess_page_and_save_from_raw_bytes()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga08dd0476f72f50bd13fc1445191b8057) methods. These methods apply preprocessing filters to the image and save the resulting image to a file.

You can use this file to analyze the effectiveness of preprocessing filters, exclude unnecessary filters that consume resources without affecting the result, or show the result of preprocessing in the user interface.

```cpp
std::string image_path = "source.png";
custom_preprocessing_filters filters_;
filters_.filter_1 = OCR_IMG_PREPROCESS_GRAYSCALE;
filters_.filter_2 = OCR_IMG_PREPROCESS_THRESHOLD(20);
filters_.filter_3 = OCR_IMG_PREPROCESS_BINARIZE;
filters_.filter_4 = OCR_IMG_PREPROCESS_RESIZE(1500, 2500);
filters_.filter_5 = OCR_IMG_PREPROCESS_SCALE(0.8);
filters_.filter_6 = OCR_IMG_PREPROCESS_DILATE;
filters_.filter_7 = OCR_IMG_PREPROCESS_ROTATE(-20);
filters_.filter_8 = OCR_IMG_PREPROCESS_INVERT;
asposeocr_preprocess_page_and_save(image_path.c_str(), "result.png", filters_);
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