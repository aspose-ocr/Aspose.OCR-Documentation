---
weight: 34
date: "2026-07-31"
author: "Anna Pylaieva"
type: docs
url: /net/document-type-detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
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

Aspose.OCR for .NET can automatically classify the content of an image or document page before running a specialized OCR workflow. This helps route mixed input batches to the most suitable recognition or post-processing pipeline.

Document type detection is available in two modes:

- `Aspose.OCR.AsposeOcr.DetectDocumentType()` uses built-in rule-based logic combined with a neural model.
- `Aspose.OCR.AsposeOcr.DetectDocumentTypeAI()` uses an AI-powered LLM workflow and returns the model response as an `AIResult`.

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

To detect document type, provide the [collection of images](/ocr/net/ocrinput/) to `Aspose.OCR.AsposeOcr.DetectDocumentType()` method.

The method returns `List<DocTypeOutput>`. Each item contains:

Property | Type | Description
-------- | ---- | -----------
`Source` | `string` | Image path or URL when available. Empty for in-memory input.
`Page` | `int` | Zero-based page number.
`DocType` | `DocType` | Detected document category.
`Confidence` | `float` | Confidence score from `0.0` to `1.0`.

```csharp
using Aspose.OCR;
using System;
using System.Collections.Generic;

AsposeOcr api = new AsposeOcr();

OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("invoice.png");

List<DocTypeOutput> results = api.DetectDocumentType(input);

foreach (DocTypeOutput result in results)
{
	Console.WriteLine($"Source: {result.Source}");
	Console.WriteLine($"Page: {result.Page}");
	Console.WriteLine($"Document type: {result.DocType}");
	Console.WriteLine($"Confidence: {result.Confidence:P0}");
}
```

## Detecting document type with AI

Use `Aspose.OCR.AsposeOcr.DetectDocumentTypeAI()` to classify documents with an AI-powered LLM workflow.

The method returns `List<Aspose.OCR.AI.AIResult>`. The `Result` property contains the model response, usually as a JSON string with document type, confidence, and reasoning.

```csharp
using Aspose.OCR;
using Aspose.OCR.AI;
using System;
using System.Collections.Generic;

AsposeOcr api = new AsposeOcr();

OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("invoice.png");

List<AIResult> results = api.DetectDocumentTypeAI(input);

foreach (AIResult result in results)
{
	Console.WriteLine($"File: {result.FileName}");
	Console.WriteLine(result.Result);
}
```

## Detecting document types in a PDF

For multi-page documents, one `DocTypeOutput` item is returned for each processed page.

```csharp
using Aspose.OCR;
using System;
using System.Collections.Generic;

AsposeOcr api = new AsposeOcr();

OcrInput input = new OcrInput(InputType.PDF);
input.Add("mixed-document.pdf", 0, 3);

List<DocTypeOutput> results = api.DetectDocumentType(input);

foreach (DocTypeOutput result in results)
{
	Console.WriteLine($"Page {result.Page}: {result.DocType} ({result.Confidence:P0})");
}
```
