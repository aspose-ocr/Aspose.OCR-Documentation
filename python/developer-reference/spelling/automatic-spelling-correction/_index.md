---
weight: 10
date: "2025-01-27"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/automatic-spelling-correction/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET can automatically replace commonly misspelled words in recognition results with the correct ones. This functionality supports the following languages:

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

Spell checking is done on the fly, either on output (`get_spell_check_corrected_text()` method) or on [saving](/ocr/python-net/save-file/) the results:

{{< tabs tabID="1" tabTotal="2" tabName1="Output corrected results" tabName2="Save corrected results" >}}
{{< tab tabNum="1" >}}
```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
result = api.recognize(input)
# Print corrected results
correctedResult = results[0].get_spell_check_corrected_text(SpellCheckLanguage.ENG)
print(correctedResult)
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
results = api.recognize(input)
# Save recognition result
results[0].save("result.txt", SaveFormat.TEXT, true, SpellCheckLanguage.DEU)
```
{{< /tab >}}
{{< /tabs >}}

{{% alert color="primary" %}}
Automatic spelling correction requires additional processing resources and is disabled by default.
{{% /alert %}}

## Spelling correction of any text

You can also correct misspelled words in any text string using `correct_spelling()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Correct spelling in string
text = "Die schönste Jungfrau sitzet dort oben wunderbar"
correctedText = api.correct_spelling(text, SpellCheckLanguage.DEU)
print(correctedText)
```
