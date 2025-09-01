---
weight: 30
date: "2024-06-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/recognition-settings-passport/
feedback: OCRPYNET
title: Passport recognition settings
description: Configuring Aspose.OCR for Python via .NET recognition engine for extracting text from passport images.
keywords:
- setting
- config
- parameter
- image
- photo
- passport
---

Aspose.OCR for Python via .NET allows for very flexible customization of passport recognition accuracy, performance, and other settings by configuring the properties of the [`PassportRecognitionSettings`](https://reference.aspose.com/ocr/python-net/aspose.ocr/passportrecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed passports.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`allowed_symbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/python-net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`ignored_symbols` | string | _none_ | A [blacklist](/ocr/python-net/characters-blacklist/) of characters that are ignored during recognition.
`language` | [`Language`](https://reference.aspose.com/ocr/python-net/aspose.ocr/language/) | `Language.NONE` | Specify a [language](/ocr/python-net/languages/) for recognition.
`automatic_color_inversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.
`country` | [`Country`](https://reference.aspose.com/ocr/python-net/aspose.ocr/country/) | `Country.NONE` | Extract key passport details (such as a number, name, date of birth, and so on) for the specific country in addition to the entire passport text.<br />See **Supported countries** section below.

## Supported countries

A list of countries for retrieving specific details (such as a number, name, date of birth, and so on) from passport images:

Value | Country
----- | -------
`Country.NONE` | Do not parse passport details (only recognize passport text).
`Country.MADAGASCAR` | Parse Malagasy passports.
`Country.USA` | Parse US passports.

## Applicable to

- [Extracting text from a passport](/ocr/python-net/recognition/passport/)

## Example

The following code example shows how to fine-tune passport recognition:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("passport1.png")
input.add("passport2.png")
# Customize recognition settings
recognitionSettings = PassportRecognitionSettings()
recognitionSettings.language = Language.LATIN
# Recognize passports
result = api.recognize_passport(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
