---
weight: 60
date: "2023-09-15"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/recognition-settings-receipt/
feedback: OCRPYNET
title: Receipt recognition settings
description: Configuring Aspose.OCR for Python via .NET recognition engine for extracting text from scanned receipts.
keywords:
- setting
- config
- parameter
- receipt
- check
- scan
---

Aspose.OCR for Python via .NET allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`ReceiptRecognitionSettings`](https://reference.aspose.com/ocr/python-net/aspose.ocr/receiptrecognitionsettings/) object.

These settings are applicable when extracting text from scanned receipts in JPEG, PNG, TIFF, BMP, and GIF formats.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`allowed_symbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/python-net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`ignored_symbols` | string | _none_ | A [blacklist](/ocr/python-net/characters-blacklist/) of characters that are ignored during recognition.
`language` | [Language](https://reference.aspose.com/ocr/python-net/aspose.ocr/language/) | `Language.NONE` | Specify a [language](/ocr/python-net/languages/) for recognition.
`upscale_small_font` | boolean | `false` | Improve small font recognition and detection of dense lines.
`automatic_color_inversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.
`threads_count` | integer | _auto_ | The number of [CPU threads](/ocr/python-net/multithreading/) used for recognition.

## Applicable to

- [Extracting text from receipts](/ocr/python-net/recognition/receipt/)

## Example

The following code example shows how to fine-tune receipt recognition:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("car1.png")
input.add("car2.png")
# Customize recognition settings
recognitionSettings = ReceiptRecognitionSettings()
recognitionSettings.language = Language.LATIN
# Recognize receipts
result = api.recognize_receipt(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
