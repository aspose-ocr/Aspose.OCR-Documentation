---
weight: 20
date: "2023-09-15"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition-settings-id-card/
feedback: OCRPYNET
title: ID card recognition settings
description: Configuring Aspose.OCR for Python via .NET recognition engine for extracting text from ID cards.
keywords:
- setting
- config
- parameter
- image
- photo
- ID
- card
---

Aspose.OCR for Python via .NET allows for very flexible customization of ID card recognition accuracy, performance, and other settings by configuring the properties of the [`IDCardRecognitionSettings`](https://reference.aspose.com/ocr/python-net/aspose.ocr/idcardrecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed ID cards.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`allowed_symbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/python-net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`ignored_symbols` | string | _none_ | A [blacklist](/ocr/python-net/characters-blacklist/) of characters that are ignored during recognition.
`language` | [Language](https://reference.aspose.com/ocr/python-net/aspose.ocr/language/) | `Language.NONE` | Specify a [language](/ocr/python-net/languages/) for recognition.
`automatic_color_inversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.
`threads_count` | integer | _auto_ | The number of [CPU threads](/ocr/python-net/multithreading/) used for recognition.

## Applicable to

- [Extracting text from an ID card](/ocr/python-net/recognition/id-card/)

## Example

The following code example shows how to fine-tune ID card recognition:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("ID1.png")
input.add("ID2.png")
# Customize recognition settings
recognitionSettings = IDCardRecognitionSettings()
recognitionSettings.language = Language.LATIN
# Recognize ID cards
result = api.recognize_id_card(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
