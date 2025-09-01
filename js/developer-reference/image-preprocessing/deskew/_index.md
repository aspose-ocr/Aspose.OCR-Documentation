---
weight: 10
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/deskew/
title: Skew correction
description: How to straighten a rotated image to improve recognition accuracy.
keywords:
- deskew
- straighten
- rotate
- tilt
- skew
- align
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

	.code-sample {
		display: flex;
	}

	.code-sample > div {
		display: flex;
		align-items: center;
		padding: 5px 10px;
		border-radius: 5px;
		white-space: nowrap;
		background-color: rgba(0,0,0,5%);
		font-size: 16px;
		font-weight: 700;
	}

	.unseen {
		display: none !important;
	}

	.duo {
		position: relative;
		width: 800px;
		height: 474px;
	}

	.duo > img {
		position: absolute;
	}
</style>

When a page is fed to a flatbed scanner (mechanically or manually) or photographed with a smartphone, it is nearly impossible to achieve perfect alignment. As a result, a slight skew (tilt) inevitably occurs in scanned images or photographs.

Skew angle detection and image straightening is critical to the OCR process as it directly affects the reliability and efficiency of segmentation and text extraction. Aspose.OCR offers automated processing algorithms to correct image tilt (deskew) before proceeding to recognition.

## Automatic skew correction

To automatically straighten skewed image before recognition, set `correct_skew` [recognition setting](/ocr/javascript-cpp/settings/) to `true`. Since most of the images have some degree of tilt, this setting is turned on by default.

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
// Even if you omit this line, the automatic skew correction will be enabled
settings.correct_skew = true;
```

<div class="duo">
	<img src="skew-origin.png" alt="Skewed image" />
	<img src="deskew.png" alt="Deskewed image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Deskew image</button>
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
			$(obj).text("Deskew image");
		}
	}
</script>

## Manual skew correction

In rare cases, automatic skew correction may incorrectly determine the angle of the image. This can happen to poor quality photos with significant perspective distortions or when the image is rotated by more than 15 degrees in either direction.

To deal with such situations, you can manually define the skew angle for such images using the `skew` property in [recognition setting](/ocr/javascript-cpp/settings/). The rotation angle is passed in degrees as a floating point number:

- `-360` to `0`: rotate counterclockwise;
- `0` to `360`: rotate clockwise.

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
// Fix rotated pages
settings.skew = -90;
```

## Usage scenarios

- Automatic skew correction is recommended in almost all cases, except for perfectly straight scans.
- Manual rotation is recommended for:
    - photos of low quality;
    - images with a significant angle of inclination.
