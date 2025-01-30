---
weight: 60
date: "2025-01-29"
author: "Vladimir Lapin"
type: docs
url: /java/recognition-settings-car-plate/
feedback: OCRJAVA
title: Car plate recognition settings
description: Configuring Aspose.OCR for Java recognition engine for extracting text from car plate images or photographs.
keywords:
- setting
- config
- parameter
- image
- photo
- car
- number
- license
---

Aspose.OCR for Java allows for very flexible customization of vehicle license plate recognition accuracy, performance, and other settings by configuring the properties of the `CarPlateRecognitionSettings` object.

These settings are specifically tailored for processing scanned or photographed vehicle license plates.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`setAllowedCharacters` | Case-sensitive string of characters or one of the predefined character sets:<ul><li>`CharactersAllowedType.ALL` - try to recognize all characters.</li><li>`CharactersAllowedType.LATIN_ALPHABET` - only recognize case-insensitive Latin / English text (`A` to `Z` and `a` to `z`), without accented characters.</li><li>`CharactersAllowedType.DIGITS` - recognize only binary, octal, decimal, or hexadecimal numbers (`0`-`9` and `A` to `F`).</li></ul> | All characters from the [selected recognition language](/ocr/java/languages/). | The [whitelist](/ocr/java/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`setIgnoredCharacters` | Case-sensitive string of characters | All characters are recognized | A [blacklist](/ocr/java/characters-blacklist/) of characters that are ignored during recognition.
`setLanguage` | [Recognition language](/ocr/java/languages/) | Latin characters without diacritics | Specify a [language](/ocr/java/languages/) for recognition.
`setAutomaticColorInversion` | boolean | `true` | Set the method parameter to `true` automatically detect white text on a dark/black background and use a special OCR algorithm to improve car license plate recognition accuracy. Call this method with the parameter set to “false” to explicitly disable inverted text detection to save resources.

## Applicable to

- [Extracting text from a car plate](/ocr/java/recognition/car-plate/)

## Example

The following code example shows how to fine-tune car plate recognition:

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "car1.png"));
input.add(os.path.join(self.dataDir, "car2.png"));
// Recognition settings
CarPlateRecognitionSettings recognitionSettings = new CarPlateRecognitionSettings();
recognitionSettings.setIgnoredCharacters("Ää");
// Recognize license plates
ArrayList<RecognitionResult> results = api.RecognizeCarPlate(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
