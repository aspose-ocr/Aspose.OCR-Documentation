---
weight: 70
date: "2024-01-25"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/read-handwritten-text/
feedback: OCRJAVA
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

Aspose.OCR for Java offers a special recognition algorithm for extracting handwritten text from images. It supports a number of European languages based on [Extended Lain alphabet](/ocr/java/recognition-languages/#supported-handwritten-characters). Handwritten recognition has various business, government and personal applications:

- Extract text from notes, memos and letters.
- Convert historical records and documents into digital formats for archival purposes.
- Parse resumes and employee records.
- Analyze information from handwritten inventory lists to maintain accurate and up-to-date databases.
- Analyze customer feedback and reviews to gain insights into customer preferences.
- And many more.

To extract handwritten text from images, use `RecognizeHandwrittenText()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class.

The method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/recognitionresult/) object containing the text from images.

```java
AsposeOCR api = new AsposeOCR();
// Load an image
OcrInput input = new OcrInput(InputType.SingleImage);
input.add("memo.png");
// Recognize handwritten text
ArrayList<RecognitionResult> result = api.RecognizeHandwrittenText(input);
out.println("Recognized text:\n" + result.get(0).recognitionText);
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

- The method only supports a [limited subset](/ocr/java/recognition-languages/#supported-handwritten-characters) of Extended Latin letters and numbers.
- Both uppercase and lowercase letters are recognized. However, the resulting text will be in uppercase.
- This method does not support recognition settings. The recognition language is detected automatically.
