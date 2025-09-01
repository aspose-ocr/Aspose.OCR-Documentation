---
weight: 40
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/recognition/invoice/
feedback: OCRJAVA
title: Extracting text from invoices
description: How to digitize scanned invoices by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- invoice
- bill
---

Even a small business may deal with dozens of printed invoices per day. Manual re-typing is time consuming and error-prone, and even a single mistake may result in significant losses.

Aspose.OCR offers a special recognition algorithm that extracts text from scanned invoices, which can then be automatically sent to accounting programs, databases or banks.

To extract text from an invoice, use `RecognizeInvoice` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-invoice/).

The method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a list of recognition results containing the invoice data.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "invoice1.png"));
input.add(os.path.join(self.dataDir, "invoice2.png"));
// Recognition settings
InvoiceRecognitionSettings recognitionSettings = new InvoiceRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Recognize invoices
ArrayList<RecognitionResult> results = api.RecognizeInvoice(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
