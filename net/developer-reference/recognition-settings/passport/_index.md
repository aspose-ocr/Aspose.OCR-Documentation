---
weight: 50
date: "2023-05-19"
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
`AllowedSymbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`IgnoredSymbols` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.

## Applicable to

- [Extracting text from a passport](/ocr/net/recognition/passport/)

## Example

The following code example shows how to fine-tune passport recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("passport1.png");
input.Add("passport2.png");
// Recognition settings
Aspose.OCR.PassportRecognitionSettings recognitionSettings = new Aspose.OCR.PassportRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize passports
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizePassport(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
