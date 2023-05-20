---
weight: 50
date: "2023-05-19"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-passport/
feedback: OCRJAVA
title: Passport recognition settings
description: Configuring Aspose.OCR for Java recognition engine for extracting text from passport images.
keywords:
- setting
- config
- parameter
- image
- photo
- passport
---

Aspose.OCR for Java allows for very flexible customization of passport recognition accuracy, performance, and other settings by configuring the properties of the `PassportRecognitionSettings` object.

These settings are specifically tailored for processing scanned or photographed passports.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`setAllowedCharacters` | Case-sensitive string of characters or one of the predefined character sets:<ul><li>`CharactersAllowedType.ALL` - try to recognize all characters.</li><li>`CharactersAllowedType.LATIN_ALPHABET` - only recognize case-insensitive Latin / English text (`A` to `Z` and `a` to `z`), without accented characters.</li><li>`CharactersAllowedType.DIGITS` - recognize only binary, octal, decimal, or hexadecimal numbers (`0`-`9` and `A` to `F`).</li></ul> | All characters from the [selected recognition language](/ocr/java/languages/). | The [whitelist](/ocr/java/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`setIgnoredCharacters` | Case-sensitive string of characters | All characters are recognized | A [blacklist](/ocr/java/characters-blacklist/) of characters that are ignored during recognition.
`setLanguage` | [Recognition language](/ocr/java/languages/) | Extended Latin characters, including diacritics | Specify a [language](/ocr/java/languages/) for recognition.
`setThreadsCount` | Number of threads, `int` | Automatic | The number of [CPU threads](/ocr/java/multithreading/) used for recognition.

## Applicable to

- [Extracting text from a passport](/ocr/java/recognition/passport/)

## Example

The following code example shows how to fine-tune passport recognition:

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "passport1.png"));
input.add(os.path.join(self.dataDir, "passport2.png"));
// Recognition settings
PassportRecognitionSettings recognitionSettings = new PassportRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Recognize license plates
results = api.RecognizePassport(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
