---
weight: 50
date: "2023-05-18"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/receipt/
feedback: OCRNET
title: Extracting text from receipts
description: How to digitize scanned receipts by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- receipt
- report
---

Almost all organizations offer their employees to reimburse travel expenses, network fees, and other payments confirmed by receipts. However, digitizing receipts is time consuming and lead to human error.

Aspose.OCR offers a special recognition algorithm that extracts text from scanned receipts, which can then be automatically sent to corporate platforms for approval and reimbursement.

To extract text from a receipt, use [`RecognizeReceipt`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizereceipt/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-receipt/).

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the receipt data.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("receipt1.png");
input.Add("receipt2.png");
// Recognition settings
Aspose.OCR.ReceiptRecognitionSettings recognitionSettings = new Aspose.OCR.ReceiptRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize receipts
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizeReceipt(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
