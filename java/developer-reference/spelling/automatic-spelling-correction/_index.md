---
weight: 10
date: "2022-09-30"
author: "Vladimir Lapin"
type: docs
url: /java/automatic-spelling-correction/
aliases:
- /java/spelling-correction/
- /java/result-correction-with-spell-checking/
title: Automatic spelling correction
description: How to automatically find and correct spelling errors in recognition results.
keywords:
- spelling
- typo
- error
- fix
- replace
- correct
---

Aspose.OCR for Java can automatically replace commonly misspelled words in recognition results with the correct ones. This functionality supports the following [languages](https://reference.aspose.com/ocr/java/com.aspose.ocr.SpellCheck/SpellCheckLanguage):

Value | Language
----- | --------
`SpellCheckLanguage.Cze` | Czech
`SpellCheckLanguage.Dan` | Danish
`SpellCheckLanguage.Deu` | German
`SpellCheckLanguage.Dum` | Dutch
`SpellCheckLanguage.Eng` | English
`SpellCheckLanguage.Est` | Estonian
`SpellCheckLanguage.Fin` | Finnish
`SpellCheckLanguage.Fra` | French
`SpellCheckLanguage.Ita` | Italian
`SpellCheckLanguage.Lav` | Latvian
`SpellCheckLanguage.Lit` | Lithuanian
`SpellCheckLanguage.Pol` | Polish
`SpellCheckLanguage.Por` | Portuguese
`SpellCheckLanguage.Rum` | Romanian
`SpellCheckLanguage.Slk` | Slovak
`SpellCheckLanguage.Slv` | Slovene
`SpellCheckLanguage.Spa` | Spanish
`SpellCheckLanguage.Swe` | Swedish

Spell checking is done on the fly, either upon [displaying](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#getSpellCheckCorrectedText--) or upon [saving](/ocr/java/save/) the results:

{{< tabs tabID="1" tabTotal="2" tabName1="Output corrected results" tabName2="Save corrected results" >}}
{{< tab tabNum="1" >}}
```java
AsposeOCR api = new AsposeOCR();
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", new RecognitionSettings());
// Output corrected text
String correctedResult = result.getSpellCheckCorrectedText(com.aspose.ocr.SpellCheck.SpellCheckLanguage.Eng);
System.out.println("Recognition result:\n" + correctedResult + "\n\n");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```java
AsposeOCR api = new AsposeOCR();
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", new RecognitionSettings());
// Save corrected text
result.saveSpellCheckCorrectedText("result.txt", Format.Json, com.aspose.ocr.SpellCheck.SpellCheckLanguage.Eng);
```
{{< /tab >}}
{{< /tabs >}}

{{% alert color="primary" %}}
Automatic spelling correction requires additional processing resources and is disabled by default.
{{% /alert %}}

## Spelling correction of any text

You can also correct misspelled words in any text string using `CorrectSpelling` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class:

```java
AsposeOCR api = new AsposeOCR();
// Extract text from image
String result = api.RecognizePage("source.png");
// Correct spelling
String correctedResult = api.CorrectSpelling(result, com.aspose.ocr.SpellCheck.SpellCheckLanguage.Eng);
System.out.println("Recognition result:\n" + correctedResult + "\n\n");
```
