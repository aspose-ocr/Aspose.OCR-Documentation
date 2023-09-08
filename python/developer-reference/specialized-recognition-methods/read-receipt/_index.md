---
weight: 50
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition/receipt/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET offers a special recognition algorithm that extracts text from scanned receipts, which can then be automatically sent to corporate platforms for approval and reimbursement.

To extract text from a receipt, use `recognize_receipt()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-receipt/).

The method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object containing the receipt data.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("receipt1.png")
input.add("receipt2.png")
# Set recognition language
recognitionSettings = ReceiptRecognitionSettings()
recognitionSettings.Language = Aspose.OCR.Language.Latin;
# Recognize license plates
results = api.recognize_receipt(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```
