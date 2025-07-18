---
weight: 40
date: "2023-12-06"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_js
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /javascript-cpp/settings/
title: Recognition settings
description: How to improve recognition accuracy and tune up Aspose.OCR for JavaScript via C++ engine.
keywords:
- configure
- settings
- options
- parameters
---

Aspose.OCR for JavaScript via C++ provides good recognition accuracy and performance out of the box. Nevertheless, there will inevitably be cases where the default settings fail to deliver dependable recognition results.

To fine-tune the recognition settings, pass an optional `Module.WasmAsposeOCRRecognitionSettings` object to the recognition function.

## Language configuration

Set the recognition language.

Setting | Value | Default value | Description
------- | ----- | ------------- | -----------
`language_alphabet` | Object | `Module.Language.NONE` | Specify a [language](/ocr/javascript-cpp/languages/) for recognition. **It is highly recommended that you always provide this setting.**
`alphabet` | String | _All symbols_ | A [custom list of characters](/ocr/javascript-cpp/characters-whitelist/) to be recognized, provided as a case-sensitive string. Characters that do not match the provided list are ignored.
`allowed_characters` | Object | `Module.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/javascript-cpp/characters-whitelist/) of characters Aspose.OCR engine will look for.
`ignoredCharacters` | String | _none_ | A [blacklist](/ocr/javascript-cpp/characters-blacklist/) of characters that are ignored during recognition.

## Document structure detection

Determine how to handle complex text layouts (multi-column texts, tables, and so on).

Setting | Value | Default value | Description
------- | ----- | ------------- | -----------
`detect_areas_mode` | `detect_areas_mode_enum` | `detect_areas_mode_enum::DOCUMENT` | Manually override the default [document areas detection model](/ocr/javascript-cpp/areas-detection/#area-detection-modes).
`lines_filtration` | Boolean | `false` | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table separators and treating tables as plain text lines.
`all_image` | Boolean | `false` | Force recognition of the entire image as a single block of text. It is recommended to enable (set to `true`) this setting only when working with very simple, one-line images.

## Preprocessing

Improve recognition accuracy for low-quality images.

Setting | Value | Default value | Description
------- | ----- | ------------- | -----------
`correct_skew` | Boolean | `true` | Automatically [correct image tilt (deskew)](/ocr/javascript-cpp/deskew/) before proceeding to recognition. Since most of the images have some degree of tilt, it is recommended to keep this setting always on.
`skew` | Floating point number | `0.0` | Manually [rotate](/ocr/javascript-cpp/deskew/#manual-skew-correction) the image by the specified degree. Recommended for significantly tilted images (by more than 15° either direction), for which the automatic skew correction may fail.<ul><li>**-360** to **0**: rotate counterclockwise;</li><li>**0** to **360**: rotate clockwise.</li></ul>
`auto_contrast` | Boolean | `false` | Automatically [increase the contrast](/ocr/javascript-cpp/contrast/) of images before proceeding to recognition. Enable for blurry images and out-of-focus photos.
`auto_denoising` | Boolean | `false` | Automatically [remove noise](/ocr/javascript-cpp/denoise/) from images before proceeding to recognition.
`upscale_small_font` | Boolean | `false` | Improve small font recognition and detection of dense lines. Recommended for endnotes, food labels and other images with small text.
`threshold_value` | Number | `0` | Override the automatic [binarization](/ocr/javascript-cpp/binarization/) settings.

## Example

The following code example shows how to fine-tune recognition:

```javascript
// Prepare images
var source = Module.WasmAsposeOCRInput();
source.url = filename;
var content = new Module.WasmAsposeOCRInputs();
content.push_back(source);
// Recognize rotated photos of book pages in Ukrainian
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.language_alphabet = Module.Language.UKR;
settings.skew = -90;
settings.detect_areas_mode = Module.DetectAreasMode.CURVED_TEXT;
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```
