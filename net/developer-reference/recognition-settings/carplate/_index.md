---
weight: 60
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-car-plate/
feedback: OCRNET
title: Car plate recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from car plate images or photographs.
keywords:
- setting
- config
- parameter
- image
- photo
- car
- number
- license
---

Aspose.OCR for .NET allows for very flexible customization of vehicle license plate recognition accuracy, performance, and other settings by configuring the properties of the [`CarPlateRecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/carplaterecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed vehicle license plates (car plates).

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedCharacters` | [Aspose.OCR.CharactersAllowedType](https://reference.aspose.com/ocr/net/aspose.ocr/charactersallowedtype/) | `Aspose.OCR.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/net/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`IgnoredCharacters` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`PreprocessingFilters` | [Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) | _none_ | Apply [image processing filters](/ocr/net/image-preprocessing/) that enhance an image before it is sent to the OCR engine.

## Applicable to

- [Extracting text from a car plate](/ocr/net/recognition/car-plate/)

## Example

The following code example shows how to fine-tune car plate recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.CarPlateRecognitionSettings recognitionSettings = new Aspose.OCR.CarPlateRecognitionSettings();
recognitionSettings.AllowedCharacters = Aspose.OCR.CharactersAllowedType.LATIN_ALPHABET;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeCarPlate("car-plate.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
