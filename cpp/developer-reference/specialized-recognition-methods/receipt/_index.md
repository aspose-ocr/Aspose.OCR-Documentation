---
weight: 30
date: "2023-07-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/receipt-recognition/
aliases:
- /cpp/recognition/receipt/
feedback: OCRCPP
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

To extract text from a receipt, use [`asposeocr_recognize_receipt()`](https://reference.aspose.com/ocr/cpp/groupAspose#ga7f7cbde7a19845e9327283489d85b62e) function. This function allows you to customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

```cpp
std::string image_path = "receipt.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
settings.upscale_small_font = true;
size_t res_len = asposeocr_recognize_receipt(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
