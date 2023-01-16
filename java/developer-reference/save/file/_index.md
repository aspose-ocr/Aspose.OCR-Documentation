---
weight: 10
date: "2023-01-16"
author: "Vladimir Lapin"
type: docs
url: /java/save-file/
aliases:
- /java/get-ocr-result-as-file/
- /java/save-ocr-result-as-multipage-document/
title: Saving recognition results as a file
description: Saving Aspose.OCR for Java recognition results as PDF, text, Word, or Excel documents, as well as XML and JSON files.
keywords:
- save
- result
- file
- PDF
- Office
- Word
- Excel
- document
- spreadsheet,
- JSON,
- XML,
- text
---

To save recognition results to a file, use `save` method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) class.

The following file formats are supported:

Format | Description
------ | -----------
`Format.Text` | Plain text with line breaks.
`Format.Pdf` | Portable Document Format.
`Format.Docx` | Microsoft Word document (version 2007 or later).
`Format.Xlsx` | Microsoft Excel spreadsheet (version 2007 or later).
`Format.Json` | JSON is a popular format widely used in software development and data exchange. The de facto standard for websites and REST APIs.
`Format.Xml` | Extensible Markup Language (XML), a universal data exchange and storage format for most systems.
`Format.Html` | HTML web page.
`Format.Epub` | ePub, a popular e-book file format.
`Format.Rtf` | RTF, a universal format for exchanging text documents between different word processing programs.

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
// Save results as PDF document
result.save("result.pdf", Format.Pdf);
```

## Saving results with automatic spelling correction

You can automatically check and correct spelling while saving the result. Use `saveSpellCheckCorrectedText` method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) class.

```java
AsposeOCR api = new AsposeOCR();
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", new RecognitionSettings());
// Save corrected text
result.saveSpellCheckCorrectedText("result.txt", Format.Json, com.aspose.ocr.SpellCheck.SpellCheckLanguage.Eng);
```

## Saving recognition results as a multi-page document

You can merge several recognition results into one document using [`SaveMultipageDocument`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#SaveMultipageDocument-java.lang.String-com.aspose.ocr.Format-java.util.ArrayList-) method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

```java
AsposeOCR api = new AsposeOCR();
// Extract text from ZIP archive
ArrayList<RecognitionResult> results = api.RecognizeMultiplePages("images.zip", new RecognitionSettings());
// Save all pages as PDF
api.SaveMultipageDocument("result.pdf", Format.Pdf, results);
```
