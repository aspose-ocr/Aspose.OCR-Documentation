---
weight: 40
date: "2023-10-26"
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

To configure Aspose.OCR recognition settings, pass an optional [`RecognitionSettings`](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/) structure to the recognition function.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`all_image` | bool | `false` | Force recognition of the entire image. Not used for [receipt recognition](/ocr/cpp/recognition/receipt/).
`allowed_characters` | `characters_allowed_type` | `characters_allowed_type::ALL` | The [predefined whitelist](/ocr/cpp/characters-whitelist/) of characters Aspose.OCR engine will look for.
`alphabet` | string | _All symbols_ | A [custom list of characters](/ocr/cpp/characters-whitelist/) to be recognized, provided as a case-sensitive string. Characters that do not match the provided list are ignored.
`auto_contrast` | bool | `false` | Automatically [increase the contrast](/ocr/cpp/contrast/) of images before proceeding to recognition.
`auto_denoising` | bool | `false` | Automatically [remove noise](/ocr/cpp/denoise/) from images before proceeding to recognition.
`correct_skew` | bool | `true` | Automatically [correct image tilt (deskew)](/ocr/cpp/deskew/) before proceeding to recognition.
`detect_areas_mode` | `detect_areas_mode_enum` | `detect_areas_mode_enum::DOCUMENT` | Manually override the default [document areas detection function](/ocr/cpp/areas-detection/#area-detection-modes). Not used for [receipt recognition](/ocr/cpp/recognition/receipt/).
`filters` | `custom_preprocessing_filters` | _none_ | [Preprocessing filters](/ocr/cpp/image-preprocessing/) to be applied to the image.
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
`defect_type` | `int` | `-1` | The type of [image defects](#detected-image-defects) that the OCR engine will look for.

## Detected image defects

The following types of image defects can be detected:

Enum | Value | Behavior
---- | ----- | --------
`ASPOSE_OCR_NONE` | 0 | Do not detect image defects (default).
`ASPOSE_OCR_DETECT_DARK_IMAGES` | 1 | Detect low contrast between text and background.<br />Such areas may not be recognized accurately, and their content may even disappear in the recognition results.
`ASPOSE_OCR_DETECT_SALT_PEPPER_NOISE` | 2 | Detect [salt-and-pepper noise](https://en.wikipedia.org/wiki/Salt-and-pepper_noise) (impulse noise) that often occurs in digital photographs taken in low light conditions. It appears as random white and black pixels.<br />This type of noise can cause certain characters to be misidentified or non-existent characters such as dots or commas to appear in recognition results.
`ASPOSE_OCR_DETECT_CURVED_TEXT` | 4 | Detect image areas containing cylindrical curvature distortions.<br />Such areas may not be recognized accurately or not recognized at all.
`ASPOSE_OCR_DETECT_BLURED_IMAGE ` | 8 | Detect blurry images, the recognition accuracy of which may be insufficient without preprocessing.<br />Unlike other defect detection algorithms, this one cannot detect individual areas of the image. If it detects blurry text, the entire image area is returned.
`ASPOSE_OCR_DETECT_GLARES` | 16 | Detect highlight areas in an image caused by uneven lighting, such as spot lights or flash.<br />Such areas usually have low contrast, which can negatively affect recognition accuracy or even lead to some texts not being recognized.
`ASPOSE_OCR_DETECT_EXTRA_BOLD_TEXT ` | 32 | Detect very thick characters on an image.<br />Such characters may be recognized incorrectly.
`ASPOSE_OCR_DETECT_ALL` | 9999 | Detect all supported image defects.

## Example

The following code example shows how to fine-tune recognition:

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Fine-tune recognition
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
settings.auto_contrast = true;
settings.upscale_small_font = true;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```
