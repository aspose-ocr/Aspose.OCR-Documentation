---
weight: 70
date: "2024-06-07"
author: "Vladimir Lapin"
type: docs
url: /java/defect-detection/
feedback: OCRJAVA
title: Defect detection
description: How to automatically find problem areas in an image that may be recognized inaccurately.
keywords:
- problems
- defects
- issues
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

	#area1 {
		top: 0px;
		left: 0px;
		width: 60px;
		height: 50px;
	}

	#area2 {
		top: 0px;
		left: 560px;
		width: 220px;
		height: 590px;
	}

	#area3 {
		top: 550px;
		left: 0px;
		width: 90px;
		height: 40px;
	}
</style>

Image defects can significantly impact the accuracy of OCR. They can be caused by the quality of the image acquisition process, environmental conditions, and the hardware used to capture the image. To improve recognition accuracy, it is essential to [preprocess and enhance](/ocr/java/image-processing/) images to mitigate these defects whenever possible.

Aspose.OCR for Java can automatically find potentially problematic areas of image and return the information on the type of defect and its coordinates. The following types of defects can be found:

Defect | Enumeration | Description | Impact | How to mitigate
------ | ----------- | ----------- | ------ | ---------------
[Salt-and-pepper noise](https://en.wikipedia.org/wiki/Salt-and-pepper_noise) | `DefectType.SALT_PEPPER_NOISE` | Appears as random white and black pixels scattered across the area. Often occurs in digital photographs. | <ul><li>Some characters are misidentified</li><li>Unnecessary dots or commas appear in recognition results</li></ul> | <ul><li>Apply [median filter](/ocr/java/median/)</li><li>Use [automatic noise removal](/ocr/java/denoise/)</li></ul>
Low contrast between text and background | `DefectType.LOW_CONTRAST` | Highlights and shadows typically appear on curved pages. | <ul><li>Low recognition accuracy</li><li>Text not recognized (ignored by OCR engine)</li></ul> | <ul><li>[Automatically adjust contrast](/ocr/java/contrast/)</li><li>[Convert to grayscale](/ocr/java/grayscale/)</li><li>[Binarize with high threshold](/ocr/java/binarization/#using-binarization-threshold)</li></ul>
Blur | `DefectType.BLUR` | The entire image or some of its areas are out of focus.<br />**Important:** This detection algorithm can only identify the entire image as blurry. Specific areas cannot be detected. | <ul><li>Characters are not recognized correctly</li><li>Text not recognized (ignored by OCR engine)</li></ul> | <ul><li>Use [automatic contrast correction](/ocr/java/contrast/)</li><li>[Convert image to grayscale](/ocr/java/grayscale/)</li></ul>
Glare | `DefectType.GLARE` | Highlight areas in an image caused by uneven lighting, such as spot lights or flash. | <ul><li>Low recognition accuracy</li><li>Text not recognized (ignored by OCR engine)</li></ul> | <ul><li>[Automatically adjust contrast](/ocr/java/contrast/)</li><li>[Convert to grayscale](/ocr/java/grayscale/)</li><li>[Binarize with high threshold](/ocr/java/binarization/#using-binarization-threshold)</li></ul>
_All supported defects_ | `DefectType.ALL` | All above-mentioned defects. | See the corresponding defect for details. | See the corresponding defect for details.

You can highlight problem areas when previewing an image and even OCR them using alternative recognition settings to get a better result.

## Detecting defects

To find defects on images, provide the [collection of images](/ocr/java/ocrinput/) and specify the type of defect to `DetectDefects()` method.

The method returns `DefectOutput` object with the following properties:

Property | Type | Description
-------- | ---- | -----------
`Source` | `string` | Image path.
`Page` | `int` | Page number of multi-page images.
`defectAreas` | `List<DefectAreas>` | The list of defects and areas of an image where they were found.

```java
// Initialize Aspose.OCR recognition API
AsposeOCR api = new AsposeOCR();
// Add image to the recognition batch
OcrInput source = new OcrInput(InputType.SingleImage);
source.add("image.png");
// Find shadows and highlights
ArrayList<DefectOutput> defects =  api.DetectDefects(input, DefectType.LOW_CONTRAST);
for(DefectOutput d : result) {
	for (DefectAreas ar : d.defectAreas) {
		System.out.println(ar.defectType);
		for (Rectangle r : ar.rectangles) {
			System.out.println(r.x + " " + r.y + " " + r.width + " " + r.height);
		}
	}
}
```

## Live demo

<div id="sample">
	<img src="demo.png" alt="Low-contrast image" />
	<div id="area1"></div>
	<div id="area2"></div>
	<div id="area3"></div>
</div>

<button onclick="extract(this)">Detect shadows and highlights</button>

<script>
	function extract(obj)
	{
		$("#sample > div").show(200);
		$("#results").show(200);
	}
</script>
