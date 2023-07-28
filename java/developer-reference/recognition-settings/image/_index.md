---
weight: 10
date: "2023-07-27"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-common/
aliases:
- /java/recognition-settings-image/
- /java/recognition-settings-document/
feedback: OCRJAVA
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
`setDetectAreasMode` | [`DetectAreasMode`](https://reference.aspose.com/ocr/java/com.aspose.ocr/DetectAreasMode) | Automatic | Manually override the default [document areas detection method](/ocr/java/areas-detection/#area-detection-modes).
`setIgnoredCharacters` | Case-sensitive string of characters | All characters are recognized | A [blacklist](/ocr/java/characters-blacklist/) of characters that are ignored during recognition.
`setLanguage` | [Recognition language](/ocr/java/languages/) | Extended Latin characters, including diacritics | Specify a [language](/ocr/java/languages/) for recognition.
`setLinesFiltration` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Enabled | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`setRecognitionAreas` | `ArrayList<Rectangle>` | Entire image | List of [areas of the image](/ocr/java/image-regions-extract/) from which to extract text.
`setRecognizeSingleLine` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Recognize a [single-line](/ocr/java/recognize-single-line/) image. Disables automatic document region detection.<br />Improves the recognition performance of simple images.
`setThreadsCount` | Number of threads, `int` | Automatic | The number of [CPU threads](/ocr/java/multithreading/) used for recognition.
`setUpscaleSmallFont` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Improve small font recognition and detection of dense lines.
`setAutomaticColorInversion` | boolean | `true` | Set the method parameter to `true` automatically detect white text on a dark/black background and use a special OCR algorithm to improve image recognition accuracy. Call this method with the parameter set to “false” to explicitly disable inverted text detection to save resources.<br />This setting is only applicable when using one of the following [document area detection modes](/ocr/java/areas-detection/):<ul><li>[`DetectAreasMode.PHOTO`](/ocr/java/areas-detection/photo/)</li><li>[`DetectAreasMode.COMBINE`](/ocr/java/areas-detection/combine/)</li><li>[`DetectAreasMode.TABLE`](/ocr/java/areas-detection/table/)</li><li>[`DetectAreasMode.CURVED_TEXT`](/ocr/java/areas-detection/curved_text/)</li></ul>

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for Java 23.3.0, these recognition settings are used as a universal replacement for image recognition settings (`RecognitionSettings`) and multi-page document recognition settings (`DocumentRecognitionSettings`).
{{% /alert %}}

## Applicable to

- [Extracting](/ocr/java/recognition/) text from images, scanned PDFs, DjVu files and other content provided as [`OcrInput` object](/ocr/java/ocrinput/).

## Example

The following code example shows how to fine-tune recognition:

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Specify recognition settings
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setAllowedCharacters(CharactersAllowedType.LATIN_ALPHABET);
recognitionSettings.setDetectAreasMode(DetectAreasMode.DOCUMENT);
recognitionSettings.setUpscaleSmallFont(true);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage, filters);
images.add("image1.png");
images.add("image2.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognitionText);
});
```
