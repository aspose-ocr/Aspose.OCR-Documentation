---
weight: 59
date: "2025-11-27"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/formula-recognition/
aliases:
- /python-net/recognition/read-text-in-wild/
feedback: OCRPYNET
title: Formula recognition
description: Extracting and recognizing formulas from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- formula
- extract
- OCR
- recognize
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
		display: flex;
		flex-direction: row;
		align-items: stretch;
		margin-bottom: 20px;
	}

	.duo > * {
		margin-bottom: 0 !important;
	}

	.duo > pre {
		display: none;
		margin-left: 15px;
		min-width: 300px;
	}
	
</style>


Aspose.OCR for Python via .NET now provides a dedicated API for detecting and recognizing mathematical formulas in images, scanned documents, screenshots, or photos.
To extract formula text, simply call the universal [`aspose.ocr.AsposeOcr.recognize_formula`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) method.

This method accepts an `OcrInput` object and optional recognition settings.
Internally, formula detection uses the [`DetectAreasMode.FORMULA`](https://reference.aspose.com/ocr/python-net/aspose.ocr/detectareasmode/) mode to locate mathematical expressions before recognition.

Recognition results are returned as a list of `aspose.ocr.RecognitionResult` objects. Each result contains extracted formula text, detected regions, and allows exporting to various formats.


## DetectAreasMode.FORMULA

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")

# Set areas detection mode
recognitionSettings = RecognitionSettings()
recognitionSettings.detect_areas_mode = DetectAreasMode.FORMULA
# Recognize the image
results = api.recognize(input, recognitionSettings)

# Print recognition result
for result in results:
    print(result.recognition_text)
```

## RecognizeFormula(OcrInput images, bool detectAreas = true)

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")

# Recognize formulas with areas detection
results = api.recognize_formula(input, True)
# Parameter bool detectAreas - if set to true, automatically detects and isolates formula regions before performing recognition. If false, processes the entire image as a formula.

# Print recognition result
for result in results:
    print(result.recognition_text)
```


## Live demo 
```csharp
recognitionEngine.recognize_formula(input, True)
```

<div class="duo">
<img src="formula1.png" alt="Formula with text" />
<img src="formula1_rect.jpg" alt="Formulas regions" style="display: none;" />
<pre class="rec-result">
x_{c} ( t )=\\sin\left( 2 \\pi( 1 0 0 ) t \right)
T=1 / 4 0 0
x [ n ]
x [ n ]
x [ n ]=\\cos\left( {\\frac{\\pi} {4}} n \right) , \\qquad-\\infty< n < \\infty.
</pre>
</div>



<button onclick="triggerRecogn(this)">Extract formulas</button>
<script>
	function triggerRecogn(obj)
	{
		let images = $(".duo > img");
		let skewed = images.eq(0).is(":visible");
		if(skewed)
		{
			images.eq(1).show(100);
			images.eq(0).hide(100);
			$(obj).text("Revert to original image");
			$('.rec-result').slideDown(100);
		}
		else
		{
			images.eq(0).show(100);
			images.eq(1).hide(100);
			$(obj).text("Extract formulas");
			$('.rec-result').slideUp(100);
		}
	}
</script>

## Live demo 
```csharp
recognitionEngine.recognize_formula(input, False)
```

<div class="duo">
<img src="formula2.png" alt="Formula without text" />
<pre class="rec-result2">
x [ n ]=\\cos\left( \\frac{\\pi} {4} n \right) . \\qquad-\\infty< n < \\infty.
</pre>
</div>

<button onclick="$('.rec-result2').slideDown(100);">Extract formulas</button>