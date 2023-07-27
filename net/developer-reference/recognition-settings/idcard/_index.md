---
weight: 20
date: "2023-07-25"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-id-card/
feedback: OCRNET
title: ID card recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from ID cards.
keywords:
- setting
- config
- parameter
- image
- photo
- ID
- card
---

Aspose.OCR for .NET allows for very flexible customization of ID card recognition accuracy, performance, and other settings by configuring the properties of the [`IDCardRecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/idcardrecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed ID cards.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedSymbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`IgnoredSymbols` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.
`AutomaticColorInversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.

## Applicable to

- [Extracting text from an ID card](/ocr/net/recognition/id-card/)

## Example

The following code example shows how to fine-tune ID card recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("ID1.png");
input.Add("ID2.png");
// Recognition settings
Aspose.OCR.IDCardRecognitionSettings recognitionSettings = new Aspose.OCR.IDCardRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize ID cards
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeIDCard(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
