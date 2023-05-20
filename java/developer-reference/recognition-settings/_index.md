---
weight: 40
date: "2023-05-19"
author: "Vladimir Lapin"
type: docs
url: /java/settings/
feedback: OCRJAVA
aliases:
- /java/recognition-settings/
- /java/setting-the-ocrengine-to-automatically-detect-the-text-blocks-in-php
- /java/setting-the-ocrengine-to-automatically-detect-the-reading-order-in-ruby
title: Recognition settings
description: How to improve recognition accuracy and tune up Aspose.OCR engine.
keywords:
- configure
- settings
- options
- parameters
---

Aspose.OCR for Java provides good recognition accuracy and performance by default. However, there will inevitably be cases where the default settings cannot provide reliable recognition results.

To configure Aspose.OCR recognition settings, specify an optional parameter for the recognition method. The parameter type depends on the recognition method.

Parameter type | Applicable to
-------------- | -------------
[`RecognitionSettings`](/ocr/java/recognition-settings-common/) | [Extracting](/ocr/java/recognition/) text from images, scanned PDFs, DjVu files and other content provided as [`OcrInput` object](/ocr/java/ocrinput/).
[`DocumentRecognitionSettings`](/ocr/java/recognition-settings-document/) | <ul><li>[Extracting text from PDF document](/ocr/java/recognition/pdf/)</li><li>[Extracting text from multi-page TIFF](/ocr/java/recognition/tiff/)</li><li>[Extracting text from multi-page DjVu](/ocr/java/recognition/djvu/)</li></ul>
[`ReceiptRecognitionSettings`](/ocr/java/recognition-settings-receipt/) | Extracting text from [receipts](/ocr/java/recognition/receipt/).
[`IDCardRecognitionSettings`](/ocr/java/recognition-settings-id-card/) | Extracting text from [ID cards](/ocr/java/recognition/id-card/).
[`PassportRecognitionSettings`](/ocr/java/recognition-settings-passport/) | Extracting text from [passports](/ocr/java/recognition/passport/).
[`CarPlateRecognitionSettings`](/ocr/java/recognition-settings-car-plate/) | Extracting text from [vehicle license plates](/ocr/java/recognition/car-plate/).
[`InvoiceRecognitionSettings`](/ocr/java/recognition-settings-invoice/) | Extracting text from [invoices](/ocr/java/recognition/invoice/).
