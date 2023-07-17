---
weight: 20
date: "2023-07-17"
author: "Vladimir Lapin"
type: docs
url: /java/misspelled-words-list/
feedback: OCRJAVA
title: Getting the list of misspelled words
description: How to get the list of misspelled words and replacement suggestions.
keywords:
- spelling
- typo
- error
- fix
- replacement
---

Aspose.OCR can automatically generate a list of misspelled words found in an image and their suggested replacements in descending order of suitability. This list is fetched using [`getSpellCheckErrorList`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#getSpellCheckErrorList-com.aspose.ocr.SpellCheck.SpellCheckLanguage-) method of [`RecognitionResult`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) class.

This functionality supports the following [languages](https://reference.aspose.com/ocr/java/com.aspose.ocr.SpellCheck/SpellCheckLanguage):

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

Found errors and suggested substitutions are provided as a list of [`SpellCheckError`](https://reference.aspose.com/ocr/java/com.aspose.ocr.SpellCheck/SpellCheckError) objects. The substitutions are ordered by [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) from the misspelled word, so the most likely replacements come first.

```java
AsposeOCR api = new AsposeOCR();
// Add an image to OcrInput object
OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");
// Recognize image
ArrayList<RecognitionResult> results = api.Recognize(input);
// Spelling suggestions
results[0].getSpellCheckErrorList(SpellCheckLanguage.Eng).forEach((correction) -> {
	System.out.println("Found misspelled word \"" + correction.word + "\" at position " + correction.startPosition);
	if(correction.suggestedWords.size() > 0) System.out.println("Most likely replacement: " + correction.get(0).word);
});
```
