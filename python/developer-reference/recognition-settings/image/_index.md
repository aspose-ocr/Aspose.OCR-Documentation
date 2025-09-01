---
weight: 10
date: "2023-09-15"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/recognition-settings-common/
feedback: OCRPYNET
title: Common recognition settings
description: Configuring Aspose.OCR for Python via .NET recognition engine for extracting text from images, scanned PDFs, DjVu files and other content.
keywords:
- setting
- config
- parameter
- image
- picture
- raster
- pdf
- document
- djvu
- pages
---

Aspose.OCR for Python via .NET allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`RecognitionSettings`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionsettings/) object.

These universal settings are applicable when extracting text from single-page and multi-page images, scanned PDFs, DjVu files, folders, archives and other content.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`allowed_symbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/python-net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`detect_areas_mode` | [DetectAreasMode](https://reference.aspose.com/ocr/python-net/aspose.ocr/detectareasmode/) | _auto_ | Manually override the default [document areas detection method](/ocr/python-net/areas-detection/#area-detection-modes).
`ignored_symbols` | string | _none_ | A [blacklist](/ocr/python-net/characters-blacklist/) of characters that are ignored during recognition.
`language` | [Language](https://reference.aspose.com/ocr/python-net/aspose.ocr/language/) | `Language.NONE` | Specify a [language](/ocr/python-net/languages/) for recognition.
`lines_filtration	` | boolean | `false` | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`recognize_single_line` | boolean | `false` | Recognize a [single-line](/ocr/python-net/recognize-single-line/) image. Disables automatic document region detection.<br />Improves the recognition performance of simple images.
`upscale_small_font` | boolean | `false` | Improve small font recognition and detection of dense lines.
`automatic_color_inversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.<br />This setting is only applicable when using one of the following [document area detection modes](/ocr/python-net/areas-detection/):<ul><li>[`DetectAreasMode.PHOTO`](/ocr/python-net/areas-detection/photo/)</li><li>[`DetectAreasMode.COMBINE`](/ocr/python-net/areas-detection/combine/)</li><li>[`DetectAreasMode.TABLE`](/ocr/python-net/areas-detection/table/)</li><li>[`DetectAreasMode.CURVED_TEXT`](/ocr/python-net/areas-detection/curved_text/)</li></ul>
`threads_count` | integer | _auto_ | The number of [CPU threads](/ocr/python-net/multithreading/) used for recognition.

## Applicable to

- [Extracting](/ocr/python-net/recognition/) text from images, scanned PDFs, DjVu files and other content provided as [`OcrInput` object](/ocr/python-net/ocrinput/).

## Example

The following code example shows how to fine-tune recognition:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add images to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")
input.add("source2.png")
# Customize recognition settings
recognitionSettings = RecognitionSettings()
recognitionSettings.language = Language.UKR
recognitionSettings.detect_areas_mode = DetectAreasMode.TABLE
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
