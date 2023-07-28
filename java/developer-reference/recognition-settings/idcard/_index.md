---
weight: 40
date: "2023-07-27"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-id-card/
feedback: OCRJAVA
title: ID card recognition settings
description: Configuring Aspose.OCR for Java recognition engine for extracting text from ID cards.
keywords:
- setting
- config
- parameter
- image
- photo
- ID
- card
---

Aspose.OCR for Java allows for very flexible customization of ID card recognition accuracy, performance, and other settings using `IDCardRecognitionSettings` object.

These settings are specifically tailored for processing scanned or photographed ID cards.

Method | Parameter | Default state | Description
------ | --------- | ------------- | -----------
`setAllowedCharacters` | Case-sensitive string of characters or one of the predefined character sets:<ul><li>`CharactersAllowedType.ALL` - try to recognize all characters.</li><li>`CharactersAllowedType.LATIN_ALPHABET` - only recognize case-insensitive Latin / English text (`A` to `Z` and `a` to `z`), without accented characters.</li><li>`CharactersAllowedType.DIGITS` - recognize only binary, octal, decimal, or hexadecimal numbers (`0`-`9` and `A` to `F`).</li></ul> | All characters from the [selected recognition language](/ocr/java/languages/). | The [whitelist](/ocr/java/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`setIgnoredCharacters` | Case-sensitive string of characters | All characters are recognized | A [blacklist](/ocr/java/characters-blacklist/) of characters that are ignored during recognition.
`setLanguage` | [Recognition language](/ocr/java/languages/) | Extended Latin characters, including diacritics | Specify a [language](/ocr/java/languages/) for recognition.
`setThreadsCount` | Number of threads, `int` | Automatic | The number of [CPU threads](/ocr/java/multithreading/) used for recognition.
`setAutomaticColorInversion` | boolean | `true` | Set the method parameter to `true` automatically detect white text on a dark/black background and use a special OCR algorithm to improve ID card recognition accuracy. Call this method with the parameter set to “false” to explicitly disable inverted text detection to save resources.

## Applicable to

- [Extracting text from an ID card](/ocr/java/recognition/id-card/)

## Example

The following code example shows how to fine-tune ID card recognition:

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput images  = new OcrInput(InputType.SingleImage);
images.add(os.path.join(self.dataDir, "ID1.png"));
images.add(os.path.join(self.dataDir, "ID2.png"));
// Recognition settings
IDCardRecognitionSettings recognitionSettings = new IDCardRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Recognize ID cards
ArrayList<RecognitionResult> results = api.RecognizeIDCard(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
