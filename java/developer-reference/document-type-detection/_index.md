---
weight: 34
date: "2026-07-31"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/document-type-detection/
feedback: OCRJAVA
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

Aspose.OCR for Java can automatically classify the content of an image or document page before running a specialized OCR workflow. This helps route mixed input batches to the most suitable recognition or post-processing pipeline.

Document type detection uses built-in rule-based logic combined with a neural model ported from Aspose.OCR for .NET.

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

To detect document type, provide the [collection of images](/ocr/java/ocrinput/) to `com.aspose.ocr.AsposeOCR.DetectDocumentType()` method.

The method returns `ArrayList<DocTypeOutput>`. Each item contains:

Property | Type | Description
-------- | ---- | -----------
`source` | `String` | Image path or URL when available. Empty for in-memory input.
`page` | `int` | Zero-based page number.
`docType` | `DocType` | Detected document category.
`confidence` | `float` | Confidence score from `0.0` to `1.0`.

```java
import com.aspose.ocr.AsposeOCR;
import com.aspose.ocr.DocTypeOutput;
import com.aspose.ocr.InputType;
import com.aspose.ocr.OcrInput;

import java.util.ArrayList;

public class DetectDocumentTypeExample {
    public static void main(String[] args) throws Exception {
        OcrInput input = new OcrInput(InputType.SingleImage);
        input.add("invoice.png");

        try (AsposeOCR api = new AsposeOCR()) {
            ArrayList<DocTypeOutput> results = api.DetectDocumentType(input);

            for (DocTypeOutput result : results) {
                System.out.println("Source: " + result.source);
                System.out.println("Page: " + result.page);
                System.out.println("Document type: " + result.docType);
                System.out.println("Confidence: " + result.confidence);
            }
        }
    }
}
```

## Detecting document types in a PDF

For multi-page documents, one `DocTypeOutput` item is returned for each processed page.

```java
import com.aspose.ocr.AsposeOCR;
import com.aspose.ocr.DocTypeOutput;
import com.aspose.ocr.InputType;
import com.aspose.ocr.OcrInput;

import java.util.ArrayList;

public class DetectDocumentTypePdfExample {
    public static void main(String[] args) throws Exception {
        OcrInput input = new OcrInput(InputType.PDF);
        input.add("mixed-document.pdf", 0, 3);

        try (AsposeOCR api = new AsposeOCR()) {
            ArrayList<DocTypeOutput> results = api.DetectDocumentType(input);

            for (DocTypeOutput result : results) {
                System.out.println("Page " + result.page + ": "
                    + result.docType + " (" + result.confidence + ")");
            }
        }
    }
}
```
