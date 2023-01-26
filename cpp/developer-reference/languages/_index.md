---
weight: 20
date: "2022-12-08"
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
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.language_alphabet = language::ukr;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```
