---
weight: 50
date: "2023-05-18"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/receipt/
feedback: OCRJAVA
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

To extract text from a receipt, use `RecognizeReceipt` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-receipt/).

The method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a list of recognition results containing the identity data.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "receipt1.png"));
input.add(os.path.join(self.dataDir, "receipt2.png"));
// Recognition settings
ReceiptRecognitionSettings recognitionSettings = new ReceiptRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Recognize license plates
results = api.RecognizeReceipt(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
