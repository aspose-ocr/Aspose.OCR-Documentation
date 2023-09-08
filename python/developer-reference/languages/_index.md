---
weight: 30
date: "2023-08-27"
author: "Vladimir Lapin"
type: docs
url: /python-net/languages/
feedback: OCRPYNET
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR for Python via .NET recognition engine.
keywords:
- language
- locale
- characters
- country
---

Aspose.OCR for Python via .NET can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in `language` property of recognition settings:

Value | Language
----- | --------
`Language.NONE` | [Extended Latin](/ocr/python-net/recognition-languages/#supported-characters) characters, including diacritics
`Language.LATIN` | [Extended Latin](/ocr/python-net/recognition-languages/#supported-characters) characters, including diacritics
`Language.CYRILLIC` | [Cyrillic](/ocr/python-net/recognition-languages/#supported-characters-1) characters
`Language.BEL` | Belorussian
`Language.BUL` | Bulgarian
`Language.CHI` | Chinese (more than 6,000 characters)
`Language.CZE` | Czech
`Language.DAN` | Danish
`Language.DEU` | German
`Language.DUM` | Dutch
`Language.ENG` | English
`Language.EST` | Estonian
`Language.FIN` | Finnish
`Language.FRA` | French
`Language.HIN` | Hindi
`Language.ITA` | Italian
`Language.KAZ` | Kazakh
`Language.LAV` | Latvian
`Language.LIT` | Lithuanian
`Language.NOR` | Norwegian
`Language.POL` | Polish
`Language.POR` | Portuguese
`Language.RUM` | Romanian
`Language.RUS` | Russian
`Language.SLK` | Slovak
`Language.SLV` | Slovene
`Language.SPA` | Spanish
`Language.SRP` | Serbian
`Language.SRP_HRV` | Serbo-Croatian
`Language.SWE` | Swedish
`Language.UKR` | Ukrainian

If this parameter is omitted, the OCR engine will assume that the text is written in [extended Latin](/ocr/python-net/recognition-languages/#supported-characters).

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Language.ENG`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source.png")
# Recognize Ukrainian text
recognitionSettings = RecognitionSettings()
recognitionSettings.language = Language.UKR
# Recognize the image
result = api.recognize(input, recognitionSettings)
# Print recognition result
print(result[0].recognition_text)
input("Press Enter to continue...")
```
