---
weight: 10
date: "2022-02-14"
author: "Vladimir Lapin"
type: docs
url: /java/save-file/
feedback: OCRJAVA
aliases:
- /java/get-ocr-result-as-file/
- /java/get-ocr-result-as-stream/
title: Saving recognition results as a file
description: Saving Aspose.OCR for Java recognition results as PDF, text, Word, or Excel documents, as well as XML and JSON files.
keywords:
- save
- result
- file
- Office
- Word
- Excel
- document
- spreadsheet,
- JSON,
- XML,
- text,
- markdown
---

To save recognition results to a file or write them to the memory stream, use `save` method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/recognitionresult/) object.

The following file formats are supported:

Format | Description
------ | -----------
`Format.Text` | Plain text with line breaks.
`Format.Pdf` | Portable Document Format. The original images are placed in the background; the recognized text is placed as an invisible but searchable and selectable overlay on top of the images.
`Format.PdfNoImg` | Portable Document Format containing only text. The original images are not saved along with the recognition results.
`Format.Docx` | Microsoft Word document (version 2007 or later).
`Format.Xlsx` | Microsoft Excel spreadsheet (version 2007 or later).
`Format.Json` | JSON is a popular format widely used in software development and data exchange. The de facto standard for websites and REST APIs.
`Format.Xml` | Extensible Markup Language (XML), a universal data exchange and storage format for most systems.
`Format.Html` | HTML web page.
`Format.Epub` | ePub, a popular e-book file format.
`Format.Rtf` | RTF, a universal format for exchanging text documents between different word processing programs.
`Format.hOcr` | hOCR, an open standard of data representation for formatted text obtained from OCR. It includes extracted text, style, layout, and other information.
`Format.Md` | Markdown. May include images if they are detected. If the recognition mode DetectAreasMode.MULTICOLUMN is selected, the output file will contain images, provided they are detected during processing.

You can optionally enable [automatic spelling corrections](/ocr/java/automatic-spelling-correction/) for recognition results, provide a [custom dictionary](/ocr/java/dictionaries/), or specify the font to be embedded into a PDF document. The latter is only applicable when saving recognition results into text-only PDF (`Format.PdfNoImg`).

```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save result
results[0].Save("result.txt", Format.Text);
```

## Saving recognition results as a multi-page document

You can merge several recognition results into one document using `SaveMultipageDocument` method of [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

You can optionally enable [automatic spelling corrections](/ocr/java/automatic-spelling-correction/) for recognition results and provide a [custom dictionary](/ocr/java/dictionaries/).

```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Save all pages to Microsoft Word document
AsposeOcr.SaveMultipageDocument("result.docx", Format.Docx, results);
```
