---
weight: 20
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /java/characters-whitelist/
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

Limiting a subset of characters instead of using the [full set](/ocr/java/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption. A list of characters can be automatically [identified](/ocr/java/characters-identify/) from an image using the built-in Aspose.OCR mechanisms.

## Predefined character subsets

To define the predefined set of characters Aspose.OCR engine will look for, provide one of the following values in [`setAllowedCharacters`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setAllowedCharacters-com.aspose.ocr.CharactersAllowedType-) method of [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) object:

Subset | Action
------ | ------
CharactersAllowedType.ALL | Try to recognize all characters.
CharactersAllowedType.LATIN_ALPHABET | Only recognize Latin / English text (`A` to `Z` and `a` to `z`), without accented characters. 
CharactersAllowedType.DIGITS | Recognize only binary, octal, decimal, or hexadecimal numbers (`0-9` and `A` to `F`).

Characters that do not match the provided subset are ignored.

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setAllowedCharacters(CharactersAllowedType.DIGITS);
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```

## Custom characters list

You can specify your own list of characters to be recognized in the constructor of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#AsposeOCR--) class or in [`setAllowedCharacters`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setAllowedCharacters-com.aspose.ocr.CharactersAllowedType-) method of [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) object. The characters are provided as a _case-sensitive_ string.

Characters that do not match the provided list are ignored.

{{< tabs tabID="1" tabTotal="2" tabName1="Through AsposeOCR constructor" tabName2="Through recognition settings" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR("AÁBCDEÉFG12345");
RecognitionResult result = api.RecognizePage("source.png", new RecognitionSettings());
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setAllowedCharacters("AÁBCDEÉFG12345");
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
{{< /tab >}}
{{< /tabs >}}
