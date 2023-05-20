---
weight: 40
date: "2023-05-18"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/invoice/
feedback: OCRNET
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

To extract text from an invoice, use [`RecognizeInvoice`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeinvoice/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-invoice/).

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the invoice data.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("invoice1.png");
input.Add("invoice2.png");
// Recognition settings
Aspose.OCR.InvoiceRecognitionSettings recognitionSettings = new Aspose.OCR.InvoiceRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize invoices
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeInvoice(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
