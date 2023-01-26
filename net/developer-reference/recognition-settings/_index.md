---
weight: 40
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/settings/
feedback: OCRNET
title: Recognition settings
description: How to improve recognition accuracy and tune up Aspose.OCR engine.
keywords:
- configure
- settings
- options
- parameters
---

Aspose.OCR for .NET provides good recognition accuracy and performance by default. However, there will inevitably be cases where the default settings cannot provide reliable recognition results.

To configure Aspose.OCR recognition settings, specify an optional parameter for the recognition method. The parameter type depends on the recognition method.

Parameter type | Applicable to
-------------- | -------------
[`RecognitionSettings`](/ocr/net/recognition-settings-image/) | <ul><li>[Extracting text from a raster image](/ocr/net/recognition/image/)</li><li>[Extracting text from pixel array](/ocr/net/recognition/pixel/)</li><li>[Extracting text from URL](/ocr/net/recognition/url/)</li></ul>
[`DocumentRecognitionSettings`](/ocr/net/recognition-settings-document/) | <ul><li>[Extracting text from PDF document](/ocr/net/recognition/pdf/)</li><li>[Extracting text from multi-page TIFF](/ocr/net/recognition/tiff/)</li><li>[Extracting text from multi-page DjVu](/ocr/net/recognition/djvu/)</li></ul>
[`ReceiptRecognitionSettings`](/ocr/net/recognition-settings-receipt/) | <ul><li>[Extracting text from receipts](/ocr/net/recognition/receipt/)</li></ul>
[`IDCardRecognitionSettings`](/ocr/net/recognition-settings-id-card/) | <ul><li>[Extracting text from ID cards](/ocr/net/recognition/id-card/)</li></ul>
[`PassportRecognitionSettings`](/ocr/net/recognition-settings-passport/) | <ul><li>[Extracting text from passports](/ocr/net/recognition/passport/)</li></ul>
[`CarPlateRecognitionSettings`](/ocr/net/recognition-settings-car-plate/) | <ul><li>[Extracting text from vehicle license plates](/ocr/net/recognition/car-plate/)</li></ul>
[`InvoiceRecognitionSettings`](/ocr/net/recognition-settings-invoice/) | <ul><li>[Extracting text from invoices](/ocr/net/recognition/invoice/)</li></ul>
