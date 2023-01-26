---
weight: 20
date: "2023-01-16"
author: "Vladimir Lapin"
type: docs
url: /java/languages/
feedback: OCRJAVA
aliases:
- /java/working-with-different-languages/
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR recognition engine.
keywords:
- language
- locale
- characters
- country
---

Aspose.OCR for Java can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in [`setLanguage`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setLanguage-com.Language-) method of [RecognitionSettings](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class:

Value | Language
----- | --------
`Language.None` | [Extended Latin](/ocr/java/recognition-languages/#supported-characters) characters, including diacritics
`Language.Latin` | [Extended Latin](/ocr/java/recognition-languages/#supported-characters) characters, including diacritics
`Language.Cyrillic` | [Cyrillic](/ocr/java/recognition-languages/#supported-characters-1) characters
`Language.Bel` | Belorussian
`Language.Bul` | Bulgarian
`Language.Chi` | Chinese (more than 6,000 characters)
`Language.Cze` | Czech
`Language.Dan` | Danish
`Language.Deu` | German
`Language.Dum` | Dutch
`Language.Eng` | English
`Language.Est` | Estonian
`Language.Fin` | Finnish
`Language.Fra` | French
`Language.Hin` | Hindi
`Language.Ita` | Italian
`Language.Kaz` | Kazakh
`Language.Lav` | Latvian
`Language.Lit` | Lithuanian
`Language.Nor` | Norwegian
`Language.Pol` | Polish
`Language.Por` | Portuguese
`Language.Rum` | Romanian
`Language.Rus` | Russian
`Language.Slk` | Slovak
`Language.Slv` | Slovene
`Language.Spa` | Spanish
`Language.Srp` | Serbian
`Language.Srp_hrv` | Serbo-Croatian
`Language.Swe` | Swedish
`Language.Ukr` | Ukrainian

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Language.Eng`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```java
AsposeOCR api = new AsposeOCR();
RecognitionSettings recognitionSettings = new RecognitionSettings();
// Recognize Ukrainian text
recognitionSettings.setLanguage(Language.Ukr);
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```
