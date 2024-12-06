---
weight: 50
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/image-line-extract/
feedback: OCRNET
aliases:
- /net/result-get-lines/
title: Extracting lines with coordinates
description: Automatic detection of line bounding boxes during recognition.
keywords:
- line
- rectangle
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

	#results {
		display: none;
		max-width: 50%;
	}
</style>

Aspose.OCR returns coordinates of each extracted line in recognition results. This can be useful for highlighting detected lines when previewing an image.

The lines are returned as a list of [`Aspose.OCR.RecognitionResult.LinesResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/recognitionlinesresult/) objects with the following fields:

Field | Type | Description
----- | ---- | -----------
`Line` | [`Aspose.Drawing.Rectangle`](https://reference.aspose.com/pdf/net/aspose.pdf.drawing/rectangle/) | Line bounding box
`TextInLine` | `string` | Extracted text

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
foreach(Aspose.OCR.RecognitionResult.LinesResult line in results[0].RecognitionLinesResult)
{
	Console.WriteLine($"{line.Line}: {line.TextInLine}");
}
```

## Live demo

<div id="sample">
	<img src="origin.png" alt="Recognized image" />
	<div style="top:30px;left:32px;width:548px;height:17px;"></div>
	<div style="top:58px;left:32px;width:562px;height:19px;"></div>
	<div style="top:88px;left:32px;width:592px;height:15px;"></div>
	<div style="top:118px;left:32px;width:578px;height:19px;"></div>
	<div style="top:148px;left:32px;width:579px;height:19px;"></div>
	<div style="top:178px;left:32px;width:389px;height:19px;"></div>
</div>

<button onclick="extract(this)">Extract lines</button>

<script>
	function extract(obj)
	{
		$("#sample > div").show(200);
		$("#results").show(200);
	}
</script>

<table id="results">
	<tr><th>Extracted line</th></tr>
	<tr><td>Optical character recognition or optical character reader (OCR) is the</td></tr>
	<tr><td>electronic or mechanical conversion of images of typed, handwritten or</td></tr>
	<tr><td>printed text into machine-encoded text. whether from a scanned document</td></tr>
	<tr><td>a photo of a document, a scene-photo (for example the text on signs and</td></tr>
	<tr><td>billboards in a landscape photo) or from subtitle text superimposed on an</td></tr>
	<tr><td>image (for example: from a television broadcast).</td></tr>
</table>
