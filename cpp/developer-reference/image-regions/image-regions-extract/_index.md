---
weight: 40
date: "2023-07-20"
author: "Vladimir Lapin"
type: docs
url: /cpp/image-regions-extract/
feedback: OCRCPP
aliases:
- /cpp/perform-ocr-on-the-selected-area-of-an-image/
title: Extracting text inside a rectangle
description: Extract text located inside areas of the image provided by coordinates.
keywords:
- area
- region
- block
- rectangle
- box
- boundary
- coordinates
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

	#sample {
		position: relative;
	}

	#sample > div {
		position: absolute;
		display: none;
		border: dashed 1px #de4444;
		background-color: rgba(222,68,68,0.2);
	}

	#dl-name {
		top: 101px;
		left: 231px;
		width: 430px;
		height: 42px;
	}

	#dl-exp {
		top: 224px;
		left: 546px;
		width: 123px;
		height: 26px;
	}

	#results {
		display: none;
		max-width: 50%;
	}
</style>

Aspose.OCR allows you to extract names, dates, numbers, and other blocks from certain areas of uniform images, such as ID cards, visas, driver's licenses, applications, and so on. Regions can be provided manually, or found automatically using the [paragraph](/ocr/cpp/image-regions-paragraph-find/), [line](/ocr/cpp/image-regions-line-find/) or [word](/ocr/cpp/image-regions-word-find/) detection.

To extract text from one or more areas of an image, provide region boundaries in `rectangles` parameter the [recognition settings](/ocr/cpp/settings/).

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set rectangles
rect rectangles[2] = { {90, 186, 775, 95} , { 928, 606, 790, 160 } };
RecognitionSettings settings;
settings.rectangles = rectangles;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
```

## Live demo

<div id="sample">
	<img src="dl.png" alt="Driver's license" />
	<div id="dl-name"></div>
	<div id="dl-exp"></div>
</div>

<button onclick="extract(this)">Extract name and expiry date</button>

<script>
	function extract(obj)
	{
		$("#sample > div").show(200);
		$("#results").show(200);
	}
</script>

<table id="results">
	<tr>
		<th>Block</th>
		<th>Coordinates</th>
		<th>Extracted text</th>
	</tr>
	<tr>
		<td>Name</td>
		<td>{X=231, Y=101, Width=430, Height=42}</td>
		<td>SAMPLE<br />AVERY JOSEPH</td>
	</tr>
	<tr>
		<td>Expiry date</td>
		<td>{X=546, Y=224, Width=123, Height=26}</td>
		<td>08/15/2022</td>
	</tr>
</table>
