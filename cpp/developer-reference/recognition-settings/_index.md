---
weight: 40
date: "2022-12-08"
author: "Vladimir Lapin"
type: docs
url: /cpp/settings/
feedback: OCRCPP
title: Recognition settings
description: How to improve recognition accuracy and tune up Aspose.OCR engine.
keywords:
- configure
- settings
- options
- parameters
---

Aspose.OCR for .NET provides good recognition accuracy and performance by default. However, there will inevitably be cases where the default settings cannot provide reliable recognition results.

To configure Aspose.OCR recognition settings, pass an optional [`RecognitionSettings`](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/) structure to the recognition method.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`all_image` | bool | `false` | Force recognition of the entire image. Not used for [receipt recognition](/ocr/cpp/recognition/receipt/).
`allowed_characters` | `characters_allowed_type` | `characters_allowed_type::ALL` | The [predefined whitelist](/ocr/cpp/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`alphabet` | string | _All symbols_ | A [custom list of characters](/ocr/cpp/characters-whitelist/#custom-characters-list) to be recognized, provided as a case-sensitive string. Characters that do not match the provided list are ignored.
`auto_contrast` | bool | `false` | Automatically [increase the contrast](/ocr/cpp/contrast/) of images before proceeding to recognition.
`auto_denoising` | bool | `false` | Automatically [remove noise](/ocr/cpp/denoise/) from images before proceeding to recognition.
`correct_skew` | bool | `true` | Automatically [correct image tilt (deskew)](/ocr/cpp/deskew/) before proceeding to recognition.
`detect_areas_mode` | `detect_areas_mode_enum` | `detect_areas_mode_enum::DOCUMENT` | Manually override the default [document areas detection method](/ocr/cpp/areas-detection/#area-detection-modes). Not used for [receipt recognition](/ocr/cpp/recognition/receipt/).
`filters` | `custom_preprocessing_filters` | _none_ | [Preprocessing filters](/ocr/cpp/image-preprocessing/) to be applied to the image.
`format` | `export_format` | `export_format::text` | The format of recognition results that are [stored in memory](/ocr/cpp/recognition/) (plain text, JSON or XML).
`ignoredCharacters` | string | _none_ | A [blacklist](/ocr/cpp/characters-blacklist/) of characters that are ignored during recognition.
`language_alphabet` | `language` | `language::none` | Specify a [language](/ocr/cpp/languages/) for recognition.
`lines_filtration` | bool | `false` | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`preprocess_area` | `rect*` | `NULL` | Specify the image region to be affected by [preprocessing filters](/ocr/cpp/image-preprocessing/). 
`rectangles` | `rect*` | `NULL` | [Areas of the image](/ocr/cpp/image-regions-extract/) from which to extract text.
`rectangles_size` | `size_t` | `0` | The number of [recognition areas](/ocr/cpp/image-regions/).
`save_format` | `file_format` | `file_format::txt` | The file format in which the recognition result is [saved](/ocr/cpp/save-file/).
`skew` | `double` | `0` | Manually [rotate](/ocr/cpp/deskew/#manual-skew-correction) the image by the specified degree. Does not work if recognition areas are specified.
`threshold_value` | `int` | `0` | [Override](/ocr/cpp/binarization/#using-binarization-threshold) the automatic binarization settings.
`upscale_small_font` | bool | `false` | Improve small font recognition and detection of dense lines.

## Example

The following code example shows how to fine-tune recognition:

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
settings.auto_contrast = true;
settings.upscale_small_font = true;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
