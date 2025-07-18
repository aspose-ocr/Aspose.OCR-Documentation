---
weight: 50
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/settings/
feedback: OCRPYNET
title: Recognition settings
description: How to improve recognition accuracy and tune up Aspose.OCR for Python via .NET engine.
keywords:
- configure
- settings
- options
- parameters
---

Aspose.OCR for Python via .NET provides good recognition accuracy and performance by default. However, there will inevitably be cases where the default settings cannot provide reliable recognition results.

To configure Aspose.OCR for Python via .NET recognition settings, specify an optional parameter for the recognition method. The parameter type depends on the recognition method.

Parameter type | Applicable to
-------------- | -------------
[`RecognitionSettings`](/ocr/python-net/recognition-settings-common/) | [Extracting](/ocr/python-net/recognition/) text from images, scanned PDFs, DjVu files and other content provided as [`OcrInput` object](/ocr/python-net/ocrinput/).
[`ReceiptRecognitionSettings`](/ocr/python-net/recognition-settings-receipt/) | Extracting text from [receipts](/ocr/python-net/recognition/receipt/).
[`IDCardRecognitionSettings`](/ocr/python-net/recognition-settings-id-card/) | Extracting text from [ID cards](/ocr/python-net/recognition/id-card/).
[`PassportRecognitionSettings`](/ocr/python-net/recognition-settings-passport/) | Extracting text from [passports](/ocr/python-net/recognition/passport/).
[`CarPlateRecognitionSettings`](/ocr/python-net/recognition-settings-car-plate/) | Extracting text from [vehicle license plates](/ocr/python-net/recognition/car-plate/).
[`InvoiceRecognitionSettings`](/ocr/python-net/recognition-settings-invoice/) | Extracting text from [invoices](/ocr/python-net/recognition/invoice/).
