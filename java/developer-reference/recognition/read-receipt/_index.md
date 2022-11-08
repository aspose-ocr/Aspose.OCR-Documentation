---
weight: 80
date: "2022-11-08"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/receipt/
title: Extracting text from receipt
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

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) object containing the receipt data.

{{< tabs tabID="1" tabTotal="2" tabName1="Read TIFF from path" tabName2="Read TIFF from memory" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
// Customize recognition
ReceiptRecognitionSettings recognitionSettings = new ReceiptRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from receipt
RecognitionResult result = api.RecognizeReceipt("receipt.png", recognitionSettings);
// Get recognition results as JSON
String resultJson = result.GetJson();
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
BufferedImage source = ImageIO.read(new File("receipt.png"));
// Customize recognition
ReceiptRecognitionSettings recognitionSettings = new ReceiptRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Extract text from receipt
RecognitionResult result = api.RecognizeReceipt(source, recognitionSettings);
// Get recognition results as JSON
String resultJson = result.GetJson();
```
{{< /tab >}}
{{< /tabs >}}
