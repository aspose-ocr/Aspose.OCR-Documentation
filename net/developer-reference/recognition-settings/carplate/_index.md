---
weight: 40
date: "2023-07-25"
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
`AllowedSymbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`IgnoredSymbols` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`AutomaticColorInversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.

## Applicable to

- [Extracting text from a car plate](/ocr/net/recognition/car-plate/)

## Example

The following code example shows how to fine-tune car plate recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("car1.png");
input.Add("car2.png");
// Recognition settings
Aspose.OCR.CarPlateRecognitionSettings recognitionSettings = new Aspose.OCR.CarPlateRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize license plates
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizeCarPlate(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
