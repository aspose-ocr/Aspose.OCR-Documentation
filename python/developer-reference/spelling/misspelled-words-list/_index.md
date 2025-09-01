---
weight: 20
date: "2025-01-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/misspelled-words-list/
feedback: OCRPYNET
title: Getting the list of misspelled words
description: How to get the list of misspelled words and replacement suggestions.
keywords:
- spelling
- typo
- error
- fix
- replacement
---

Aspose.OCR for Python via .NET can automatically generate a list of misspelled words found in an image and their suggested replacements in descending order of suitability. This list is fetched using `get_spell_check_error_list()` method of [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object.

This functionality supports the following languages:

Value | Language
----- | --------
`SpellCheckLanguage.CES` | Czech
`SpellCheckLanguage.DAN` | Danish
`SpellCheckLanguage.DEU` | German
`SpellCheckLanguage.NLD` | Dutch
`SpellCheckLanguage.ENG` | English
`SpellCheckLanguage.EST` | Estonian
`SpellCheckLanguage.FIN` | Finnish
`SpellCheckLanguage.FRA` | French
`SpellCheckLanguage.ITA` | Italian
`SpellCheckLanguage.LAV` | Latvian
`SpellCheckLanguage.LIT` | Lithuanian
`SpellCheckLanguage.POL` | Polish
`SpellCheckLanguage.POR` | Portuguese
`SpellCheckLanguage.RON` | Romanian
`SpellCheckLanguage.SLK` | Slovak
`SpellCheckLanguage.SLV` | Slovene
`SpellCheckLanguage.SPA` | Spanish
`SpellCheckLanguage.SWE` | Swedish

Found errors and suggested substitutions are provided as a list of [`SpellCheckError`](https://reference.aspose.com/ocr/python-net/aspose.ocr.spellchecker/spellcheckerror/) objects. The substitutions are ordered by [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) from the misspelled word, so the most likely replacements come first.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
result = api.recognize(input)
# Output misspelled words
errors = results[0].get_spell_check_error_list(SpellCheckLanguage.ENG)
for error in errors:
    print("Found misspelled word: " + error.word)
    if len(error.suggested_words)>0:
        print("Most likely replacement: " + error.suggested_words[0].word)
```
