---
weight: 30
date: "2022-09-02"
author: "Vladimir Lapin"
type: docs
url: /net/dictionaries/
title: Working with custom dictionaries
description: How to create and apply custom dictionaries for Aspose.OCR spell checker.
keywords:
- spelling
- dictionary
- glossary
---

The recognized text may contain specialized terminology, abbreviations, and other words which are not present in common spelling dictionaries. To overcome these situations, you can provide your own word lists in addition to Aspose.OCR's built-in dictionaries.

The user dictionary is provided as a UTF-8 encoded plain text file with Windows or Unix line endings. Each word is provided in lowercase on a separate line, followed by its frequency separated from the word by a single space or tab.

The path to the custom dictionary file can be provided in all [spell checking](/ocr/net/spelling/) methods.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
string correctedResult = result.GetSpellCheckCorrectedText(Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng, "dictionary.txt");
Console.WriteLine(correctedResult);
```
