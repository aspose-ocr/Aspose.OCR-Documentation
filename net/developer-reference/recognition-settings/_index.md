---
weight: 40
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /net/settings/
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
