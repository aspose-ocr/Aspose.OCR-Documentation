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
`Module.Language.none`    | 0             | [Extended Latin](/ocr/javascript-cpp/recognition-languages/#supported-characters) characters, including diacritics
`Module.Language.bel`     | 22            | Belorussian
`Module.Language.bul`     | 23            | Bulgarian
`Module.Language.chi`     | 21            | Chinese
`Module.Language.cze`     | 7             | Czech
`Module.Language.dan`     | 8             | Danish
`Module.Language.deu`     | 2             | German
`Module.Language.dum`     | 9             | Dutch
`Module.Language.eng`     | 1             | English
`Module.Language.est`     | 10            | Estonian
`Module.Language.fin`     | 11            | Finnish
`Module.Language.fra`     | 5             | French
`Module.Language.hin`     | 28            | Hindi
`Module.Language.ita`     | 6             | Italian
`Module.Language.kaz`     | 27            | Kazakh
`Module.Language.lav`     | 12            | Latvian
`Module.Language.lit`     | 13            | Lithuanian
`Module.Language.nor`     | 14            | Norwegian
`Module.Language.pol`     | 15            | Polish
`Module.Language.por`     | 3             | Portuguese
`Module.Language.rum`     | 16            | Romanian
`Module.Language.rus`     | 24            | Russian
`Module.Language.slk`     | 18            | Slovak
`Module.Language.slv`     | 19            | Slovene
`Module.Language.spa`     | 4             | Spanish
`Module.Language.srp`     | 25            | Serbian
`Module.Language.srp_hrv` | 17            | Serbo-Croatian
`Module.Language.swe`     | 20            | Swedish
`Module.Language.ukr`     | 26            | Ukrainian

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `Module.Language.eng`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters may be misinterpreted as similar-looking alternatives or ignored completely.
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
settings.language_alphabet = Module.Language.deu;
// Recognize image
var result = Module.AsposeOCRRecognize(content, settings);
```
