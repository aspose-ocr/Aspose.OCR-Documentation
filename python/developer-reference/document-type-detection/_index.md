---
weight: 34
date: "2026-07-31"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/document-type-detection/
feedback: OCRPYNET
title: Document type detection
description: How to automatically identify whether an image or page contains an invoice, table, formula, handwritten text, book page, presentation, picture, or scientific document.
keywords:
- document
- type
- classification
- detect
- invoice
- table
- handwritten
---

Aspose.OCR for Python via .NET can automatically classify the content of an image or document page before running a specialized OCR workflow. This helps route mixed input batches to the most suitable recognition or post-processing pipeline.

Document type detection is available in two modes:

- `AsposeOcr.detect_document_type()` uses built-in rule-based logic combined with a neural model.
- `AsposeOcr.detect_document_type_ai()` uses an AI-powered LLM workflow and returns the model response as an `AIResult`.

## Supported document types

The following document categories can be detected:

Document type | Description
------------- | -----------
`DocType.UNKNOWN` | Document type was not detected.
`DocType.PICTURE` | Photo, advertisement, billboard, packaging, or similar visual content.
`DocType.HANDWRITTEN` | Handwritten content.
`DocType.BOOK` | Book page or other primarily textual content.
`DocType.FORMULA` | Mathematical formula, equation, or expression.
`DocType.TABLE` | Table, form, or spreadsheet-like content.
`DocType.PRESENTATION` | Presentation slide.
`DocType.SCIENTIFIC` | Scientific article, report, paper, or technical publication.
`DocType.INVOICE` | Invoice, bill, receipt, or payment document.

## Detecting document type

To detect document type, provide the [collection of images](/ocr/python-net/ocrinput/) to `detect_document_type()` method.

The method returns a list of `DocTypeOutput` objects. Each item contains:

Property | Description
-------- | -----------
`source` | Image path or URL when available. Empty for in-memory input.
`page` | Zero-based page number.
`doc_type` | Detected document category.
`confidence` | Confidence score from `0.0` to `1.0`.

```python
import aspose.ocr

api = aspose.ocr.AsposeOcr()

input_data = aspose.ocr.OcrInput(aspose.ocr.InputType.SINGLE_IMAGE)
input_data.add("invoice.png")

results = api.detect_document_type(input_data)

for result in results:
    print("Source:", result.source)
    print("Page:", result.page)
    print("Document type:", result.doc_type)
    print(f"Confidence: {result.confidence:.0%}")
```

## Detecting document type with AI

Use `detect_document_type_ai()` to classify documents with an AI-powered LLM workflow.

The method returns a list of `aspose.ocr.ai.AIResult` objects. The `result` property contains the model response, usually as a JSON string with document type, confidence, and reasoning.

```python
import aspose.ocr

api = aspose.ocr.AsposeOcr()

input_data = aspose.ocr.OcrInput(aspose.ocr.InputType.SINGLE_IMAGE)
input_data.add("invoice.png")

results = api.detect_document_type_ai(input_data)

for result in results:
    print("File:", result.file_name)
    print(result.result)
```

## Detecting document types in a PDF

For multi-page documents, one result item is returned for each processed page.

```python
import aspose.ocr

api = aspose.ocr.AsposeOcr()

input_data = aspose.ocr.OcrInput(aspose.ocr.InputType.PDF)
input_data.add("mixed-document.pdf", 0, 3)

results = api.detect_document_type(input_data)

for result in results:
    print(f"Page {result.page}: {result.doc_type} ({result.confidence:.0%})")
```
