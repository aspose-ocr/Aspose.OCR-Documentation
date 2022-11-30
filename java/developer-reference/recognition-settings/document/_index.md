---
weight: 20
date: "2022-09-27"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-document/
title: Multi-page document recognition settings
description: Configuring Aspose.OCR for Java recognition engine for extracting text from multi-page images and PDF documents.
keywords:
- setting
- config
- parameter
- pdf
- document
- TIF
- TIFF
- pages
---

Aspose.OCR for Java allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`DocumentRecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/DocumentRecognitionSettings) object.

These settings are applicable when extracting text from multi-page TIFF images and scanned PDF documents.

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
`setPagesNumber` | Number of pages, `int` | 1 | The number of pages to be recognized in a multi-page file.
`setSkew` | Skew angle, `double` | 0 | Manually [rotate](/ocr/java/deskew/#manual-skew-correction) the image by the specified degree.
`setStartPage` | Page number, `int` | First page | The page number from which to start recognition of the multi-page file. The first page number is `0`.
`setThreadsCount` | Number of threads, `int` | Automatic | The number of [CPU threads](/ocr/java/multithreading/) used for recognition.
`setThresholdValue` | Binarization threshold, `int` | Automatic | [Override](/ocr/java/binarization/#using-binarization-threshold) the automatic binarization settings.
`setUpscaleSmallFont` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Improve small font recognition and detection of dense lines.

## Applicable to

- [Extracting text from PDF document](/ocr/java/recognition/pdf/)
- [Extracting text from multi-page TIFF](/ocr/java/recognition/tiff/)

## Example

The following code example shows how to fine-tune recognition:

```java
// Create instance of OCR API
AsposeOCRPdf api = new AsposeOCRPdf();
// Specify recognition settings
DocumentRecognitionSettings recognitionSettings = new DocumentRecognitionSettings();
recognitionSettings.setStartPage(3);
recognitionSettings.setPagesNumber(10);
recognitionSettings.setLanguage(Language.Fra);
// Extract text from image
ArrayList<RecognitionResult> results = api.RecognizePdf("source.pdf", recognitionSettings);
// Save results to Microsoft Word document
AsposeOCR ocr = new AsposeOCR();
ocr.SaveMultipageDocument("result.docx", Format.Docx, results);
```