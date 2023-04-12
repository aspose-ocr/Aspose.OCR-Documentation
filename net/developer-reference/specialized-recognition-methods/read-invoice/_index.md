---
weight: 40
date: "2023-01-17"
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

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the invoice data.

{{< tabs tabID="1" tabTotal="2" tabName1="Read invoice from path" tabName2="Read invoice from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.InvoiceRecognitionSettings recognitionSettings = new Aspose.OCR.InvoiceRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeInvoice("invoice.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.InvoiceRecognitionSettings recognitionSettings = new Aspose.OCR.InvoiceRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("invoice.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeInvoice(ms, recognitionSettings);
		Console.WriteLine(result.RecognitionText);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
