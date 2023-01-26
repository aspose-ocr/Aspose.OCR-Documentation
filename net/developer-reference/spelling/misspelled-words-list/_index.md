---
weight: 20
date: "2022-09-02"
author: "Vladimir Lapin"
type: docs
url: /net/misspelled-words-list/
feedback: OCRNET
title: Getting the list of misspelled words
description: How to get the list of misspelled words and replacement suggestions.
keywords:
- spelling
- typo
- error
- fix
- replacement
---

Aspose.OCR can automatically generate a list of misspelled words found in an image and their suggested replacements in descending order of suitability. This list is fetched using [`GetSpellCheckErrorList`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/getspellcheckerrorlist/) method of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object.

This functionality supports the following languages:

Value | Language
----- | --------
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Cze` | Czech
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Dan` | Danish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Deu` | German
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Dum` | Dutch
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng` | English
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Est` | Estonian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Fin` | Finnish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Fra` | French
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Ita` | Italian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Lav` | Latvian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Lit` | Lithuanian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Pol` | Polish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Por` | Portuguese
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Rum` | Romanian
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Slk` | Slovak
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Slv` | Slovene
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Spa` | Spanish
`Aspose.OCR.SpellChecker.SpellCheckLanguage.Swe` | Swedish

Found errors and suggested substitutions are provided as a list of [`SpellCheckError`](https://reference.aspose.com/ocr/net/aspose.ocr.spellchecker/spellcheckerror/) objects. The substitutions are ordered by [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) from the misspelled word, so the most likely replacements come first.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
foreach(var correction in result.GetSpellCheckErrorList(Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng))
{
	Console.WriteLine($@"Found misspelled word ""{correction.Word}"" at position {correction.StartPosition}.");
	if(correction.SuggestedWords.Count>0) Console.WriteLine($@"Most likely replacement: ""{correction.SuggestedWords[0].Word}""");
}
```
