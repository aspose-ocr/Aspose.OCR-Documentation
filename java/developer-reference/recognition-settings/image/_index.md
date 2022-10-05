---
weight: 10
date: "2022-09-27"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-image/
title: Image recognition settings
description: Configuring Aspose.OCR for Java recognition engine for extracting text from images.
keywords:
- setting
- config
- parameter
- image
- picture
- raster
---

Aspose.OCR for Java allows for very flexible customization of recognition accuracy, performance, and other settings by calling the methods of the [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) object.

These settings are applicable when extracting text from single-page raster images in JPEG, PNG, TIFF, BMP, and GIF formats.

Method | Parameter | Default state | Description
------ | --------- | ------------- | -----------
`setAllowedCharacters` | Case-sensitive string of characters or one of the predefined character sets:<ul><li>`CharactersAllowedType.ALL` - try to recognize all characters.</li><li>`CharactersAllowedType.LATIN_ALPHABET` - only recognize case-insensitive Latin / English text (`A` to `Z` and `a` to `z`), without accented characters.</li><li>`CharactersAllowedType.DIGITS` - recognize only binary, octal, decimal, or hexadecimal numbers (`0`-`9` and `A` to `F`).</li></ul> | All characters from the [selected recognition language](/ocr/java/languages/). | The [whitelist](/ocr/java/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`setAutoContrast` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Automatically [increase the contrast](/ocr/java/contrast/) of images before proceeding to recognition.
`setAutoDenoising` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Automatically [remove noise](/ocr/java/denoise/) from images before proceeding to recognition.
`setAutoSkew` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Enabled | Automatically [correct image tilt (deskew)](/ocr/java/deskew/) before proceeding to recognition.
`setDetectAreas` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Enabled | Automatically select the optimal [areas detection algorithm](/ocr/java/areas-detection/) that suits the most common use cases.
`setDetectAreasMode` | [`DetectAreasMode`](https://reference.aspose.com/ocr/java/com.aspose.ocr/DetectAreasMode) | Automatic | Manually override the default [document areas detection method](/ocr/java/areas-detection/#area-detection-modes).
`setIgnoredCharacters` | Case-sensitive string of characters | All characters are recognized | A [blacklist](/ocr/java/characters-blacklist/) of characters that are ignored during recognition.
`setLanguage` | [Recognition language](/ocr/java/languages/) | Extended Latin characters, including diacritics | Specify a [language](/ocr/java/languages/) for recognition.
`setLinesFiltration` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Enabled | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`setPreprocessingFilters` | [Image preprocessing filter](/ocr/java/image-preprocessing/) | None | Apply [image processing filters](/ocr/java/image-preprocessing/) that enhance an image before it is sent to the OCR engine.
`setRecognitionAreas` | `ArrayList<Rectangle>` | Entire image | List of [areas of the image](/ocr/java/image-regions-extract/) from which to extract text.
`setRecognizeSingleLine` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Recognize a [single-line](/ocr/java/recognize-single-line/) image. Disables automatic document region detection.<br />Improves the recognition performance of simple images.
`setSkew` | Skew angle, `double` | 0 | Manually [rotate](/ocr/java/deskew/#manual-skew-correction) the image by the specified degree.
`setThreadsCount` | Number of threads, `int` | Automatic | The number of [CPU threads](/ocr/java/multithreading/) used for recognition.
`setThresholdValue` | Binarization threshold, `int` | Automatic | [Override](/ocr/java/binarization/#using-binarization-threshold) the automatic binarization settings.
`setUpscaleSmallFont` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Improve small font recognition and detection of dense lines.

## Applicable to

- [Extracting text from a raster image](/ocr/java/recognition/image/)
- [Extracting text from pixel array](/ocr/java/recognition/pixel/)
- [Extracting text from URL](/ocr/java/recognition/url/)

## Example

The following code example shows how to fine-tune recognition:

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Specify recognition settings
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setAllowedCharacters(CharactersAllowedType.LATIN_ALPHABET);
recognitionSettings.setAutoDenoising(true);
recognitionSettings.setDetectAreasMode(DetectAreasMode.DOCUMENT);
recognitionSettings.setSkew(90);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
