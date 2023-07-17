---
weight: 20
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
url: /java/characters-whitelist/
feedback: OCRJAVA
aliases:
- /java/provide-allowed-characters-during-ocr-operation/
title: Defining the whitelist of characters
description: How to limit the set of characters Aspose.OCR engine will look for.
keywords:
- whitelist
- symbols
- characters
- letters
- allow
---

Limiting a subset of characters instead of using the [full set](/ocr/java/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption. A list of characters can be automatically [identified](/ocr/net/characters-identify/) from an image using the built-in Aspose.OCR mechanisms.

You can define a list of characters Aspose.OCR engine will look for by specifying them as a _case-sensitive_ string in [`setAllowedCharacters`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setAllowedCharacters-com.aspose.ocr.CharactersAllowedType-) method of [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) object.

Alternatively, you can use the [preset](https://reference.aspose.com/ocr/java/com.aspose.ocr/charactersallowedtype/):

Preset | Subset of characters
------ | --------------------
CharactersAllowedType.ALL | All characters.
CharactersAllowedType.LATIN_ALPHABET | Latin / English text (`A` to `Z` and `a` to `z`), without accented characters. 
CharactersAllowedType.DIGITS | Binary, octal, decimal, or hexadecimal numbers (`0-9` and `A` to `F`).

Characters that do not match the provided list are ignored.

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setAllowedCharacters(CharactersAllowedType.DIGITS);
// Prepare batch
OcrInput images = new OcrInput(InputType.SingleImage, filters);
images.add("image.png");
// Recognize images
ArrayList<RecognitionResult> results = api.Recognize(input, recognitionSettings);
System.out.println(results[0].recognitionText);
```

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for Java 23.3.0, this recognition setting replaces the `alphabet` parameter of `AsposeOcr` class constructor.
{{% /alert %}}
