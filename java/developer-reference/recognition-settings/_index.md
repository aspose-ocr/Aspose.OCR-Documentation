---
weight: 40
date: "2022-09-27"
author: "Vladimir Lapin"
type: docs
url: /java/settings/
aliases:
- /ocr/java/setting-the-ocrengine-to-automatically-detect-the-text-blocks-in-php
- /ocr/java/setting-the-ocrengine-to-automatically-detect-the-reading-order-in-ruby
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
[`RecognitionSettings`](/ocr/java/recognition-settings-image/) | <ul><li>[Extracting text from a raster image](/ocr/java/recognition/image/)</li><li>[Extracting text from pixel array](/ocr/java/recognition/pixel/)</li><li>[Extracting text from URL](/ocr/java/recognition/url/)</li></ul>
[`DocumentRecognitionSettings`](/ocr/java/recognition-settings-document/) | <ul><li>[Extracting text from PDF document](/ocr/java/recognition/pdf/)</li><li>[Extracting text from multi-page TIFF](/ocr/java/recognition/tiff/)</li><li>[Extracting text from multi-page DjVu](/ocr/java/recognition/djvu/)</li></ul>
[`ReceiptRecognitionSettings`](/ocr/java/recognition-settings-receipt/) | <ul><li>[Extracting text from receipts](/ocr/java/recognition/receipt/)</li></ul>
