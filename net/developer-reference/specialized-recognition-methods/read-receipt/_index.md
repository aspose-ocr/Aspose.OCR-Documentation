---
weight: 50
date: "2023-04-07"
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

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the receipt data.

{{< tabs tabID="1" tabTotal="2" tabName1="Read receipt from path" tabName2="Read receipt from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.ReceiptRecognitionSettings recognitionSettings = new Aspose.OCR.ReceiptRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeReceipt("receipt.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.ReceiptRecognitionSettings recognitionSettings = new Aspose.OCR.ReceiptRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("receipt.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeReceipt(ms, recognitionSettings);
		Console.WriteLine(result.RecognitionText);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
