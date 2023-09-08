---
weight: 30
date: "2023-09-02"
author: "Vladimir Lapin"
type: docs
url: /python-net/dictionaries/
feedback: OCRPYNET
title: Working with custom dictionaries
description: How to create and apply custom dictionaries for Aspose.OCR for Python via .NET spell checker.
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

The path to the custom dictionary file can be provided in all [spell checking](/ocr/python-net/spelling/) methods.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize the image
result = api.recognize(input)
# Print corrected results
correctedResult = results[0].get_spell_check_corrected_text(SpellCheckLanguage.ENG, "dictionary.txt")
print(correctedResult)
```
