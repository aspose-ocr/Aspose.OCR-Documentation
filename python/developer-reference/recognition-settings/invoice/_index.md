---
weight: 50
date: "2023-09-15"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition-settings-invoice/
feedback: OCRPYNET
title: Invoice recognition settings
description: Configuring Aspose.OCR for Python via .NET recognition engine for extracting text from invoice images.
keywords:
- setting
- config
- parameter
- image
- photo
- invoice
- bill
---

Aspose.OCR for Python via .NET allows for very flexible customization of invoice recognition accuracy, performance, and other settings by configuring the properties of the [`InvoiceRecognitionSettings`](https://reference.aspose.com/ocr/python-net/aspose.ocr/invoicerecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed invoices.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`allowed_symbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/python-net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`ignored_symbols` | string | _none_ | A [blacklist](/ocr/python-net/characters-blacklist/) of characters that are ignored during recognition.
`language` | [Language](https://reference.aspose.com/ocr/python-net/aspose.ocr/language/) | `Language.NONE` | Specify a [language](/ocr/python-net/languages/) for recognition.
`automatic_color_inversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.
`threads_count` | integer | _auto_ | The number of [CPU threads](/ocr/python-net/multithreading/) used for recognition.

## Applicable to

- [Extracting text from an invoice](/ocr/python-net/recognition/invoice/)

## Example

The following code example shows how to fine-tune invoice recognition:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("invoice1.png")
input.add("invoice2.png")
# Customize recognition settings
recognitionSettings = InvoiceRecognitionSettings()
recognitionSettings.language = Language.LATIN
# Recognize invoices
result = api.recognize_invoice(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
