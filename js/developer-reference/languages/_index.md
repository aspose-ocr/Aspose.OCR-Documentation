---
weight: 20
date: "2023-12-04"
author: "Vladimir Lapin"
type: docs
url: /javascript-cpp/languages/
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR for JavaScript via C++ recognition engine.
keywords:
- language
- locale
- characters
- country
---

Aspose.OCR for JavaScript via C++ can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in `language_alphabet` property in [recognition settings](/ocr/javascript-cpp/settings/):

Value                     | Numeric value | Language
------------------------- | ------------- | --------
`Module.Language.NONE`    | 0             | [Extended Latin](/ocr/javascript-cpp/recognition-languages/#supported-characters) characters, including diacritics
`Module.Language.BEL`     | 22            | Belorussian
`Module.Language.BUL`     | 23            | Bulgarian
`Module.Language.CHI`     | 21            | Chinese
`Module.Language.CZE`     | 7             | Czech
`Module.Language.DAN`     | 8             | Danish
`Module.Language.DEU`     | 2             | German
`Module.Language.DUM`     | 9             | Dutch
`Module.Language.ENG`     | 1             | English
`Module.Language.EST`     | 10            | Estonian
`Module.Language.FIN`     | 11            | Finnish
`Module.Language.FRA`     | 5             | French
`Module.Language.HIN`     | 28            | Hindi
`Module.Language.ITA`     | 6             | Italian
`Module.Language.KAZ`     | 27            | Kazakh
`Module.Language.LAV`     | 12            | Latvian
`Module.Language.LIT`     | 13            | Lithuanian
`Module.Language.NOR`     | 14            | Norwegian
`Module.Language.POL`     | 15            | Polish
`Module.Language.POR`     | 3             | Portuguese
`Module.Language.RUM`     | 16            | Romanian
`Module.Language.RUS`     | 24            | Russian
`Module.Language.SLK`     | 18            | Slovak
`Module.Language.SLV`     | 19            | Slovene
`Module.Language.SPA`     | 4             | Spanish
`Module.Language.SRP`     | 25            | Serbian
`Module.Language.SRP_HRV` | 17            | Serbo-Croatian
`Module.Language.SWE`     | 20            | Swedish
`Module.Language.UKR`     | 26            | Ukrainian

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Module.Language.ENG`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters may be misinterpreted as similar-looking alternatives or ignored completely.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```javascript
// Prepare images
var source = Module.WasmAsposeOCRInput();
source.url = filename;
var content = new Module.WasmAsposeOCRInputs();
content.push_back(source);
// Set recognition language
var settings = Module.WasmAsposeOCRRecognitionSettings();
settings.language_alphabet = Module.Language.DEU;
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```
