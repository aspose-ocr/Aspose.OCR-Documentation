---
weight: 15
date: "2024-04-23"
author: "Vladimir Lapin"
type: docs
url: /java/save-stream/
feedback: OCRJAVA
title: Saving recognition results into a stream
description: Saving the recognition results of multi-page documents (PDF, Word, and so on) into a memory stream.
keywords:
- save
- result
- stream
- pages
- Office
- Word
- PDF
- document
---

You can merge several recognition results into one document using `SaveMultipageDocument` method of [`AsposeOcr`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

The resulting document can be saved into into [OutputStream](https://docs.oracle.com/javase/8/docs/api/java/io/OutputStream.html) object.

```java
// Initialize Aspose.OCR recognition API
AsposeOCR api = new AsposeOCR();
// Add scanned PDF to the recognition batch
OcrInput source = new OcrInput(InputType.PDF);
source.add("scan.pdf");
// Recognize a document
ArrayList<RecognitionResult> results = api.Recognize(source);
// Create a stream for storing recognition results
OutputStream stream = new ByteArrayOutputStream();
// Save searchable PDF into memory stream
AsposeOCR.SaveMultipageDocument(stream, Format.Pdf, results);
```
