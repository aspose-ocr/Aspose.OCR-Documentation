---
weight: 80
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/recognition/receipt/
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

To extract text from a receipt, use [`recognize_receipt()`](https://reference.aspose.com/ocr/cpp/groupAspose#gad6ee0f380aeea5adafdee65a241f7030) method. This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/cpp/settings/).

```cpp
std::string image_path = "receipt.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
settings.upscale_small_font = true;
size_t res_len = aspose::ocr::recognize_receipt(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
