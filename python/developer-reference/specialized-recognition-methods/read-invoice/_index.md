---
weight: 40
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition/invoice/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET offers a special recognition algorithm that extracts text from scanned invoices, which can then be automatically sent to accounting programs, databases or banks.

To extract text from an invoice, use `recognize_invoice()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-invoice/).

The method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns `OcrOutput` object containing the invoice data.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("invoice1.png")
input.add("invoice2.png")
# Set recognition language
recognitionSettings = InvoiceRecognitionSettings()
recognitionSettings.Language = Aspose.OCR.Language.Latin;
# Recognize invoices
results = api.recognize_invoice(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```
