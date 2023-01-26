---
weight: 50
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-passport/
feedback: OCRNET
title: Passport recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from passport images.
keywords:
- setting
- config
- parameter
- image
- photo
- passport
---

Aspose.OCR for .NET allows for very flexible customization of passport recognition accuracy, performance, and other settings by configuring the properties of the [`PassportRecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/passportrecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed passports.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedCharacters` | [Aspose.OCR.CharactersAllowedType](https://reference.aspose.com/ocr/net/aspose.ocr/charactersallowedtype/) | `Aspose.OCR.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/net/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`AutoSkew` | boolean | `true` | Automatically [correct image tilt (deskew)](/ocr/net/deskew/) before proceeding to recognition.
`IgnoredCharacters` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`PreprocessingFilters` | [Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) | _none_ | Apply [image processing filters](/ocr/net/image-preprocessing/) that enhance an image before it is sent to the OCR engine.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.

## Applicable to

- [Extracting text from a passport](/ocr/net/recognition/passport/)

## Example

The following code example shows how to fine-tune passport recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.PassportRecognitionSettings recognitionSettings = new Aspose.OCR.PassportRecognitionSettings();
recognitionSettings.AllowedCharacters = Aspose.OCR.CharactersAllowedType.LATIN_ALPHABET;
recognitionSettings.ThreadsCount = 2;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizePassport("passport.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
