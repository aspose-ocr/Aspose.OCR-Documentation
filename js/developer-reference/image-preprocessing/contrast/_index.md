---
weight: 30
date: "2022-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/contrast/
title: Contrast correction
description: How to automatically increase image contrast to improve recognition accuracy.
keywords:
- contrast
- brightness
- black
- white
- details
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
		height: 324px;
		margin-bottom: 20px;
	}

	.duo > img {
		position: absolute;
	}
</style>

Low contrast and blurring are the most typical distortions when text is photographed with a smartphone camera, especially in low light conditions. They make it difficult for the OCR algorithms to operate successfully, significantly reducing the recognition accuracy.

Aspose.OCR for JavaScript via C++ can automatically increase the contrast of images before proceeding to recognition.

{{% alert color="primary" %}} 
Contrast correction automatically converts the image to black and white.
{{% /alert %}}

To automatically increase the image contrast before recognition, set `auto_contrast` [recognition setting](/ocr/javascript-cpp/settings/) to `true`.

```javascript
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.auto_contrast = true;
```

<div class="duo">
	<img src="origin.png" alt="Low-contrast image" />
	<img src="result.png" alt="High-contrast image" style="display: none;" />
</div>
<button onclick="triggerSkew(this)">Increase contrast</button>
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
			$(obj).text("Increase contrast");
		}
	}
</script>

## Usage scenarios

Automatic contrast adjustment is recommended for the following images:

- Photos, especially those taken in low light conditions without optical or digital image stabilization.
- Old papers.
- Text on a background.
