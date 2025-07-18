---
weight: 10
date: "2025-01-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/save-file/
feedback: OCRPYNET
title: Saving recognition results as a file
description: Saving Aspose.OCR for Python via .NET recognition results as PDF, text, Word, or Excel documents, as well as XML and JSON files.
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
- text
- markdown
---

To save recognition results to a file or write them to the memory stream, use `save()` method of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object.

The following file formats are supported:

Format | Description
------ | -----------
`SaveFormat.TEXT` | Plain text with line breaks.
`SaveFormat.PDF` | Portable Document Format. The original images are placed in the background; the recognized text is placed as an invisible but searchable and selectable overlay on top of the images.
`SaveFormat.PDF_NO_IMG` | Portable Document Format containing only text. The original images are not saved along with the recognition results.
`SaveFormat.DOCX` | Microsoft Word document (version 2007 or later).
`SaveFormat.XLSX` | Microsoft Excel spreadsheet (version 2007 or later).
`SaveFormat.JSON` | JSON is a popular format widely used in software development and data exchange. The de facto standard for websites and REST APIs.
`SaveFormat.XML` | Extensible Markup Language (XML), a universal data exchange and storage format for most systems.
`SaveFormat.HTML` | HTML web page.
`SaveFormat.EPUB` | ePub, a popular e-book file format.
`SaveFormat.RTF` | RTF, a universal format for exchanging text documents between different word processing programs.
`SaveFormat.HOCR` | hOCR, an open standard of data representation for formatted text obtained from OCR. It includes extracted text, style, layout, and other information.
`SaveFormat.MD` | Markdown.

You can optionally enable [automatic spelling corrections](/ocr/python-net/automatic-spelling-correction/) for recognition results, provide a [custom dictionary](/ocr/python-net/dictionaries/), or specify the font to be embedded into a PDF document. The latter is only applicable when saving recognition results into text-only PDF (`SaveFormat.PDF_NO_IMG`).

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
results = api.recognize(input)
# Save recognition result
results[0].save("result.txt", SaveFormat.TEXT)
```

## Saving recognition results as a multi-page document

You can merge several recognition results into one document using `save_multipage_document()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

You can optionally enable [automatic spelling corrections](/ocr/python-net/automatic-spelling-correction/) for recognition results and provide a [custom dictionary](/ocr/python-net/dictionaries/).

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("page1.png")
input.add("page2.png")
input.add("page3.png")
# Recognize the image
results = api.recognize(input)
# Save recognition result
save_multipage_document("result.docx", SaveFormat.DOCX, results)
```
