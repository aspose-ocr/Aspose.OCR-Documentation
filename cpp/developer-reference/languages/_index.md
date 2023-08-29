---
weight: 20
date: "2023-07-18"
author: "Vladimir Lapin"
type: docs
url: /cpp/languages/
feedback: OCRCPP
aliases:
- /cpp/working-with-different-languages/
title: Recognition languages
description: How to specify the language that is used by the Aspose.OCR recognition engine.
keywords:
- language
- locale
- characters
- country
---

Aspose.OCR for C++ can recognize a text in a large number of languages and all popular writing scripts, including texts with mixed languages.

To specify a language for recognition, provide one of the following values in `language_alphabet` property in [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings):

Value | Language
----- | --------
`language::none` | [Extended Latin](/ocr/cpp/recognition-languages/#supported-characters) characters, including diacritics
`language::bel` | Belorussian
`language::bul` | Bulgarian
`language::chi` | Chinese (more than 6,000 characters)
`language::cze` | Czech
`language::dan` | Danish
`language::deu` | German
`language::dum` | Dutch
`language::eng` | English
`language::est` | Estonian
`language::fin` | Finnish
`language::fra` | French
`language::hin` | Hindi
`language::ita` | Italian
`language::kaz` | Kazakh
`language::lav` | Latvian
`language::lit` | Lithuanian
`language::nor` | Norwegian
`language::pol` | Polish
`language::por` | Portuguese
`language::rum` | Romanian
`language::rus` | Russian
`language::slk` | Slovak
`language::slv` | Slovene
`language::spa` | Spanish
`language::srp` | Serbian
`language::srp_hrv` | Serbo-Croatian
`language::swe` | Swedish
`language::ukr` | Ukrainian

If this parameter is omitted, the OCR engine will assume that the text is written in extended Latin.

{{% alert color="primary" %}}
Make sure you specify the correct language for the image. If you try to recognize Cyrillic text using `language::Eng`, only the characters that look the same in both languages (for example, `с` and `c`) will be correctly recognized. Other characters will be replaced with similar-looking alternatives.
{{% /alert %}}

## Example

The following code sample demonstrates how to specify the recognition language:

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Set recognition language
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
```
