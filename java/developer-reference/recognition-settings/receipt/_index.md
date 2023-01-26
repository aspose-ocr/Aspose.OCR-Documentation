---
weight: 30
date: "2022-09-27"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-receipt/
feedback: OCRJAVA
title: Receipt recognition settings
description: Configuring Aspose.OCR for Java recognition engine for extracting text from scanned receipts.
keywords:
- setting
- config
- parameter
- receipt
- check
- scan
---

Aspose.OCR for Java allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`ReceiptRecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ReceiptRecognitionSettings) object.

These settings are applicable when extracting text from scanned receipts in JPEG, PNG, TIFF, BMP, and GIF formats.

Method | Parameter | Default state | Description
------ | --------- | ------------- | -----------
`setAllowedCharacters` | Case-sensitive string of characters or one of the predefined character sets:<ul><li>`CharactersAllowedType.ALL` - try to recognize all characters.</li><li>`CharactersAllowedType.LATIN_ALPHABET` - only recognize case-insensitive Latin / English text (`A` to `Z` and `a` to `z`), without accented characters.</li><li>`CharactersAllowedType.DIGITS` - recognize only binary, octal, decimal, or hexadecimal numbers (`0`-`9` and `A` to `F`).</li></ul> | All characters from the [selected recognition language](/ocr/java/languages/). | The [whitelist](/ocr/java/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`setAutoSkew` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Enabled | Automatically [correct image tilt (deskew)](/ocr/java/deskew/) before proceeding to recognition.
`setIgnoredCharacters` | Case-sensitive string of characters | All characters are recognized | A [blacklist](/ocr/java/characters-blacklist/) of characters that are ignored during recognition.
`setLanguage` | [Recognition language](/ocr/java/languages/) | Extended Latin characters, including diacritics | Specify a [language](/ocr/java/languages/) for recognition.
`setPreprocessingFilters` | [Image preprocessing filter](/ocr/java/image-preprocessing/) | None | Apply [image processing filters](/ocr/java/image-preprocessing/) that enhance an image before it is sent to the OCR engine.
`setThreadsCount` | Number of threads, `int` | Automatic | The number of [CPU threads](/ocr/java/multithreading/) used for recognition.
`setUpscaleSmallFont` | <ul><li>`true` - enable</li><li>`false` - disable</li></ul> | Disabled | Improve small font recognition and detection of dense lines.

## Applicable to

- [Extracting text from receipts](/ocr/java/recognition/receipt/)

## Example

The following code example shows how to fine-tune receipt recognition:

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Specify recognition settings
ReceiptRecognitionSettings recognitionSettings = new ReceiptRecognitionSettings();
recognitionSettings.setLanguage(Language.Fra);
recognitionSettings.setThreadsCount(2);
// Extract text from receipt
RecognitionResult result = api.RecognizeReceipt("receipt.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
