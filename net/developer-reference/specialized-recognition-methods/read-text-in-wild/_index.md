---
weight: 60
date: "2024-09-27"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/read-text-in-wild/
feedback: OCRNET
title: Extracting text from street photos
description: How to extract text from street photos, price tags, menus, catalogs and other images with sparse text and noisy/colored backgrounds.
keywords:
- read
- extract
- OCR
- recognize
- photo
- sign
- street
---

<style>
	button {
		cursor: pointer;
		margin-right: 20px;
		margin-bottom: 20px;
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
		height: 227px;
		margin-bottom: 20px;
	}

	.duo > div {
		display: flex;
	}

	.rec-result > pre {
		margin-left: 15px;
		min-width: 222px;
	}
</style>

Aspose.OCR offers a special recognition algorithm for extracting content from images with sparse text and noisy/colored backgrounds. This method significantly improves OCR accuracy in the following business cases:

- Read text from street photos.
- Segment and identify road signs and signboards within street images.
- Locate price tags and interpret the extracted text as prices.
- Find and aggregate regions of interest on food labels, such as nutritional information or ingredient lists.
- Identify and analyze car license plates.
- Extract text from menus and catalogs.

To extract text from such images, use [`RecognizeStreetPhoto()`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizestreetphoto/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the text from images.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("photo1.png");
input.Add("photo2.png");
// Recognize images
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeStreetPhoto(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Live demo

<div class="duo">
	<div class="rec-source"><img src="label-source.png" alt="Street photo" /></div>
	<div class="rec-result" style="display: none;">
	<img src="label-regions.png" alt="Recognition result" />
	<pre>
p
within
the
lines
only		
	</pre>
	</div>
</div>
<button onclick="triggerSkew(this)">Read label</button>
<script>
	function triggerSkew(obj)
	{
		let isOrigin = $(".rec-source").is(":visible");
		if(isOrigin)
		{
			$(".rec-source").hide();
			$(".rec-result").show();
			$(obj).text("View original photo");
		}
		else
		{
			$(".rec-source").show();
			$(".rec-result").hide();
			$(obj).text("Read label");
		}
	}
</script>
