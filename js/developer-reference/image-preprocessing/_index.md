---
weight: 15
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/image-preprocessing/
title: Image preprocessing
description: Automatic or manual actions for formatting an image before sending it for recognition.
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

The accuracy and reliability of text recognition is highly dependent on the quality of the original image. Aspose.OCR for JavaScript via C++ offers a large number of fully automated and manual image processing filters that enhance an image before it is sent to the OCR engine.

Each preprocessing filter increases the image processing time. The approximate amount of additional time required for pre-processing (as a percentage of the minimum image processing pipeline) is listed in the **Performance Impact** column.

Filter | Action | Performance impact | Usage scenarios
------ | ------ | ------------------ | ---------------
[Skew correction](/ocr/javascript-cpp/deskew/#automatic-skew-correction) | Automatically straighten images aligned at a slight angle to the horizontal. | 12% | Skewed images
[Rotation](/ocr/javascript-cpp/deskew/#manual-skew-correction) | Manually rotate severely skewed images. | 7.5% | Significantly rotated images
[Noise removal](/ocr/javascript-cpp/denoise/) | Automatically remove dirt, spots, scratches, glare, unwanted gradients, and other noise from photos and scans. | 175% extra time<br />38% more memory&nbsp;<sup>(1)</sup> | Photos<br />Old books<br />Newspapers<br />Postcards<br />Documents with stains and dirt
[Contrast correction](/ocr/javascript-cpp/contrast/) | Automatically adjust the image contrast. | 7.5% | Photos<br />Old papers<br />Text on a background
[Binarization](/ocr/javascript-cpp/binarization/) | Convert images to black and white automatically or manually adjust the criteria that determines whether a pixel is considered black or white. | 0.9%&nbsp;<sup>(2)</sup> | Used for text areas detection and most automatic image adjustments.


{{% alert color="primary" %}}
**Notes**

1. Automatic noise removal uses a powerful artificial intelligence algorithm that consumes significant computing resources and RAM. Use it with care, especially if end-users will work on entry-level desktops, Chromebooks and tablets.
2. Most OCR internal processing involves automatic conversion of images to back and white, thus the binarization settings do not have any significant effect on overall performance.
{{% /alert %}}

## Applying multiple preprocessing filters

Multiple preprocessing filters can be applied to the same image to further improve the recognition quality. Note that each filter requires additional time and resources on the computer running the application. Do not add extra filters if you are satisfied with the recognition accuracy.

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
</div>

<div class="highlight"><pre tabindex="0" class="chroma"><code class="language-javascript hljs" data-lang="javascript"><span class="line"><span class="cl"><span class="kd"><span class="hljs-keyword">var</span></span> <span class="nx">settings</span> <span class="o">=</span> <span class="nx">Module</span><span class="p">.</span><span class="nx">WasmAsposeOCRRecognitionSettings</span><span class="p">();</span>
</span></span><span class="line hidden" id="threshold-code"><span class="cl"><span class="nx">settings</span><span class="p">.</span><span class="nx">threshold_value</span> <span class="o">=</span> <span class="p">{</span><span class="nx">THRESHOLD</span><span class="p">};</span>
</span></span><span class="line hidden" id="deskew-code"><span class="cl"><span class="nx">settings</span><span class="p">.</span><span class="nx">correct_skew</span> <span class="o">=</span> <span class="kc"><span class="hljs-literal">true</span></span><span class="p">;</span>
</span></span><span class="line hidden" id="rotate-code"><span class="cl"><span class="nx">settings</span><span class="p">.</span><span class="nx">skew</span> <span class="o">=</span> <span class="p">{</span><span class="nx">ANGLE</span><span class="p">};</span>
</span></span><span class="line hidden" id="denoise-code"><span class="cl"><span class="nx">settings</span><span class="p">.</span><span class="nx">auto_denoising</span> <span class="o">=</span> <span class="kc"><span class="hljs-literal">true</span></span><span class="p">;</span>
</span></span><span class="line hidden" id="contrast-code"><span class="cl"><span class="nx">settings</span><span class="p">.</span><span class="nx">auto_contrast</span> <span class="o">=</span> <span class="kc"><span class="hljs-literal">true</span></span><span class="p">;</span>
</span></span></code></pre></div>

**Approximate increase of processing time: <span id="impact-time">0</span>%**

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