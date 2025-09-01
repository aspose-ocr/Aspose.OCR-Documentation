---
weight: 40
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/recognition-settings-car-plate/
feedback: OCRPYNET
title: Car plate recognition settings
description: Configuring Aspose.OCR for Python via .NET recognition engine for extracting text from car plate images or photographs.
keywords:
- setting
- config
- parameter
- image
- photo
- car
- number
- license
---

Aspose.OCR for Python via .NET allows for very flexible customization of vehicle license plate recognition accuracy, performance, and other settings by configuring the properties of the [`CarPlateRecognitionSettings`](https://reference.aspose.com/ocr/python-net/aspose.ocr/carplaterecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed vehicle license plates (car plates).

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`allowed_symbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/python-net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`ignored_symbols` | string | _none_ | A [blacklist](/ocr/python-net/characters-blacklist/) of characters that are ignored during recognition.
`language` | [Language](https://reference.aspose.com/ocr/python-net/aspose.ocr/language/) | `Language.NONE` | Specify a [language](/ocr/python-net/languages/) for recognition.
`automatic_color_inversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.

## Applicable to

- [Extracting text from a car plate](/ocr/python-net/recognition/car-plate/)

## Example

The following code example shows how to fine-tune car plate recognition:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("car1.png")
input.add("car2.png")
# Customize recognition settings
recognitionSettings = CarPlateRecognitionSettings()
recognitionSettings.language = Language.LATIN
# Recognize license plates
result = api.recognize_car_plate(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
