---
weight: 70
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/read-handwritten-text/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Extracting handwritten text
description: How to extract text from notes, memos, checks and other handwritten documents.
keywords:
- read
- extract
- OCR
- recognize
- note
- memo
- handwriting
- write
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

{{% alert color="caution" %}} 
To use this recognition method, [install](/ocr/net/modules/) handwritten text recognition (**aspose-ocr-handwriting-v1**) in your project.
{{% /alert %}}

Aspose.OCR offers a special recognition algorithm for extracting handwritten text from images. It supports a number of European languages based on [Extended Lain alphabet](/ocr/net/recognition-languages/#supported-handwritten-characters). Handwritten recognition has various business, government and personal applications:

- Extract text from notes, memos and letters.
- Convert historical records and documents into digital formats for archival purposes.
- Parse resumes and employee records.
- Analyze information from handwritten inventory lists to maintain accurate and up-to-date databases.
- Analyze customer feedback and reviews to gain insights into customer preferences.
- And many more.

To extract handwritten text from images, use [`RecognizeHandwrittenText()`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizehandwrittentext/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the text from images.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("memo1.png");
input.Add("memo2.png");
// Recognize images
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizeHandwrittenText(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Live demo

<div class="duo">
	<img src="handwriting.png" alt="Handwritten note" />
	<pre class="rec-result">
WE STARF WITH GOOD
BECAUSE ALL BUSINESSES SHOULD
BE DOING SOMETHING GOOD
	</pre>
</div>
<button onclick="$('.duo > pre').slideDown(100)">Extract text</button>

## Limitations

- The method only supports a [limited subset](/ocr/net/recognition-languages/#supported-handwritten-characters) of Extended Latin letters and numbers.
- Both uppercase and lowercase letters are recognized. However, the resulting text will be in uppercase.
- This method does not support recognition settings. The recognition language is detected automatically.
