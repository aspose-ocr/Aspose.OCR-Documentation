---
weight: 30
date: "2022-09-30"
author: "Vladimir Lapin"
type: docs
url: /java/dictionaries/
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

The path to the custom dictionary file can be provided with [`useUserDictionary`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#useUserDictionary-java.lang.String-) method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) class.

```java
AsposeOCR api = new AsposeOCR();
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", new RecognitionSettings());
// Use custom dictionary
result.useUserDictionary("dictionary.txt");
// Output corrected results
String correctedResult = result.getSpellCheckCorrectedText(com.aspose.ocr.SpellCheck.SpellCheckLanguage.Eng);
System.out.println("Recognition result:\n" + correctedResult + "\n\n");
```
