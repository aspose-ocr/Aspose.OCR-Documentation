---
weight: 20
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /net/languages/
aliases:
- /net/working-with-different-languages/
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR recognition engine.
keywords:
- language
- locale
- characters
- country
---

Aspose.OCR for .NET can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in [`Language`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/language/) property of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/):

Value | Language
----- | --------
`Aspose.OCR.Language.None` | [Extended Latin](/ocr/net/recognition-languages/#supported-characters) characters, including diacritics
`Aspose.OCR.Language.Latin` | [Extended Latin](/ocr/net/recognition-languages/#supported-characters) characters, including diacritics
`Aspose.OCR.Language.Cyrillic` | [Cyrillic](/ocr/net/recognition-languages/#supported-characters-1) characters
`Aspose.OCR.Language.Bel` | Belorussian
`Aspose.OCR.Language.Bul` | Bulgarian
`Aspose.OCR.Language.Chi` | Chinese (more than 6,000 characters)
`Aspose.OCR.Language.Cze` | Czech
`Aspose.OCR.Language.Dan` | Danish
`Aspose.OCR.Language.Deu` | German
`Aspose.OCR.Language.Dum` | Dutch
`Aspose.OCR.Language.Eng` | English
`Aspose.OCR.Language.Est` | Estonian
`Aspose.OCR.Language.Fin` | Finnish
`Aspose.OCR.Language.Fra` | French
`Aspose.OCR.Language.Ita` | Italian
`Aspose.OCR.Language.Kaz` | Kazakh
`Aspose.OCR.Language.Lav` | Latvian
`Aspose.OCR.Language.Lit` | Lithuanian
`Aspose.OCR.Language.Nor` | Norwegian
`Aspose.OCR.Language.Pol` | Polish
`Aspose.OCR.Language.Por` | Portuguese
`Aspose.OCR.Language.Rum` | Romanian
`Aspose.OCR.Language.Rus` | Russian
`Aspose.OCR.Language.Slk` | Slovak
`Aspose.OCR.Language.Slv` | Slovene
`Aspose.OCR.Language.Spa` | Spanish
`Aspose.OCR.Language.Srp` | Serbian
`Aspose.OCR.Language.Srp_hrv` | Serbo-Croatian
`Aspose.OCR.Language.Swe` | Swedish
`Aspose.OCR.Language.Ukr` | Ukrainian

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Aspose.OCR.Language.Eng`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
// Recognize Ukrainian text
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
