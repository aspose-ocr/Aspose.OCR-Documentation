---
weight: 10
date: "2023-07-20"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/save-file/
feedback: OCRCPP
aliases:
- /cpp/save-ocr-result-as-multipage-document/
- /cpp/get-ocr-result-as-file/
title: Saving recognition results as a file
description: Saving Aspose.OCR for C++ recognition results as PDF, text, Word, or Excel documents, as well as JSON or XML files.
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

To save recognition results to a file or write them to the memory stream, use [`asposeocr_page_save()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga471631a25e3e645880b07975b4478d9d) function.

The file format is defined by `save_format` property of [recognition settings](/ocr/cpp/settings/). The following formats are supported:

Format | Description
------ | -----------
`file_format::txt` | Plain text with line breaks.
`file_format::pdf` | Portable Document Format.
`file_format::docx` | Microsoft Word document (version 2007 or later).
`file_format::format_rtf` | RTF, a universal format for exchanging rich text documents between different word processing programs.
`file_format::xlsx` | Microsoft Excel spreadsheet (version 2007 or later).
`file_format::format_json` | JSON is a popular format widely used in software development and data exchange. The de facto standard for websites and REST APIs.
`file_format::format_xml` | Extensible Markup Language (XML), a universal data exchange and storage format for most systems.

```cpp
directory dir(".");
const string current_dir = dir.full_name();
const string image = current_dir + "p.png";
const size_t len = 6000;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.save_format = file_format::docx;
asposeocr_page_save(image.c_str(), "result.docx", settings);
```

## Saving recognition results as a multi-page document

You can merge several recognition results into one document. Simply provide several images as a semicolon-separated string to [`asposeocr_page_save()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga471631a25e3e645880b07975b4478d9d) function. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

```cpp
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.save_format = file_format::pdf;
asposeocr_page_save("1.png;2.jpg;3.jpg", "result.pdf", settings);
```

When saving recognition results in PDF format, the original image is placed as the background of the resulting document. The recognized text is added as an invisible overlay on top of the background image, and can be searched and copied to the clipboard.
