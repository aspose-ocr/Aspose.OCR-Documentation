---
weight: 20
date: "2022-08-22"
author: "Vladimir Lapin"
type: docs
url: /net/characters-whitelist/
aliases:
- /net/provide-allowed-characters-during-ocr-operation/
title: Defining the whitelist of characters
description: How to limit the set of characters Aspose.OCR engine will look for.
keywords:
- whitelist
- symbols
- characters
- letters
- allow
---

Limiting a subset of characters instead of using the [full set](/ocr/net/recognition-languages/) can greatly improve recognition accuracy, increase speed, and reduce resource consumption. A list of characters can be automatically [identified](/ocr/net/characters-identify/) from an image using the built-in Aspose.OCR mechanisms.

## Predefined character sets

To define the predefined set of characters Aspose.OCR engine will look for, provide one of the following values in [`AllowedCharacters`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/allowedcharacters/) property of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/):

Subset | Action
------ | ------
Aspose.OCR.CharactersAllowedType.ALL | Try to recognize all characters.
Aspose.OCR.CharactersAllowedType.LATIN_ALPHABET | Only recognize Latin / English text (`A` to `Z` and `a` to `z`), without accented characters. 
Aspose.OCR.CharactersAllowedType.DIGITS | Recognize only binary, octal, decimal, or hexadecimal numbers (`0-9` and `A` to `F`).

Characters that do not match the provided subset are ignored.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AllowedCharacters = Aspose.OCR.CharactersAllowedType.DIGITS;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```

## Custom characters list

You can specify your own list of characters to be recognized in the constructor of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/asposeocr/) class. The characters are provided as a _case-sensitive_ string.

Characters that do not match the provided list are ignored.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr("AÁBCDEÉFG12345");
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", new Aspose.OCR.RecognitionSettings());
Console.WriteLine(result.RecognitionText);
```
