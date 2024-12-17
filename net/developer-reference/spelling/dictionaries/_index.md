---
weight: 30
date: "2022-09-02"
author: "Vladimir Lapin"
type: docs
url: /net/dictionaries/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Working with custom dictionaries
description: How to create and apply custom dictionaries for Aspose.OCR spell checker.
keywords:
- spelling
- dictionary
- glossary
---

The recognized text may contain specialized terminology, abbreviations, and other words which are not present in common spelling dictionaries. This may cause these words to be considered errors and incorrectly replaced by the spelling corrector. To overcome these situations, you can provide your own word lists in addition to Aspose.OCR's built-in dictionaries. The words present in the dictionary will be considered correct.

For example, if the text contains the phrase _"Helloo, world!"_, it will be automatically corrected to _"Hello, world!"_. However, if you add the word _"helloo"_ to the dictionary, the phrase will remain unchanged.

## Dictionary file format

The user dictionary is provided as a UTF-8 encoded text file with Windows or Unix line endings. Each word is provided in lowercase on a separate line, followed by its frequency separated from the word by a single space or tab:

```
helloo 20000
heloo 22000
helooo 19998
```

The path to the custom dictionary file can be provided in all [spell checking](/ocr/net/spelling/) methods.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Check spelling with custom dictionary
string correctedResult = results[0].GetSpellCheckCorrectedText(Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng, "dictionary.txt");
Console.WriteLine(correctedResult);
```
