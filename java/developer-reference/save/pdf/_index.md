---
weight: 11
date: "2023-07-17"
author: "Vladimir Lapin"
type: docs
url: /java/save-searchable-pdf/
feedback: OCRJAVA
aliases:
- /java/save-ocr-result-as-multipage-document/
title: Saving recognition results as a searchable PDF
description: Saving Aspose.OCR for Java recognition results as a searchable and indexable PDF document.
keywords:
- save
- result
- file
- PDF
---

To convert recognition results into a searchable and indexable PDF document, use `SaveMultipageDocument` method of [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition. Provide `SaveFormat.Pdf` as `saveFormat` parameter.

In addition to the recognized text, you can save the resulting PDF may have original images in the background and a transparent text overlay that can be searched, selected and copied. The type of the PDF document is controlled by the selected result type option:

Format | Description
------ | -----------
`Format.Pdf` | The original images are placed in the background; the recognized text is placed as an invisible but searchable and selectable overlay on top of the images. Can be useful if you need to keep all notes, images, marks and other data along with the text.
`Format.PdfNoImg` | The PDF document containing only the recognized text. The original images are not saved along with the recognition results. This can be useful when digitizing large amounts of high-quality text (such as books) so that the resulting file takes up much less space than using the `SaveFormat.Pdf` parameter.

You can optionally enable [automatic spelling corrections](/ocr/java/automatic-spelling-correction/) for recognition results and provide a [custom dictionary](/ocr/java/dictionaries/).

{{< tabs tabID="1" tabTotal="2" tabName1="Add images below text" tabName2="Save text only" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save all pages to PDF document
AsposeOcr.SaveMultipageDocument("result.pdf", Format.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save all pages to PDF document
AsposeOcr.SaveMultipageDocument("result.pdf", Format.PdfNoImg, results);
```
{{< /tab >}}
{{< /tabs >}}
