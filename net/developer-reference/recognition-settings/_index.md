---
weight: 50
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/settings/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
aliases:
- /net/recognition-settings/
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
[`RecognitionSettings`](/ocr/net/recognition-settings-common/) | [Extracting](/ocr/net/recognition/) text from images, scanned PDFs, DjVu files and other content provided as [`OcrInput` object](/ocr/net/ocrinput/).
[`ReceiptRecognitionSettings`](/ocr/net/recognition-settings-receipt/) | Extracting text from [receipts](/ocr/net/recognition/receipt/).
[`IDCardRecognitionSettings`](/ocr/net/recognition-settings-id-card/) | Extracting text from [ID cards](/ocr/net/recognition/id-card/).
[`PassportRecognitionSettings`](/ocr/net/recognition-settings-passport/) | Extracting text from [passports](/ocr/net/recognition/passport/).
[`CarPlateRecognitionSettings`](/ocr/net/recognition-settings-car-plate/) | Extracting text from [vehicle license plates](/ocr/net/recognition/car-plate/).
[`InvoiceRecognitionSettings`](/ocr/net/recognition-settings-invoice/) | Extracting text from [invoices](/ocr/net/recognition/invoice/).
