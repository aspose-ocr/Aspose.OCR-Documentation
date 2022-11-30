---
weight: 30
date: "2022-09-23"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-receipt/
title: Receipt recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from scanned receipts.
keywords:
- setting
- config
- parameter
- receipt
- check
- scan
---

Aspose.OCR for .NET allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`ReceiptRecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/receiptrecognitionsettings/) object.

These settings are applicable when extracting text from scanned receipts in JPEG, PNG, TIFF, BMP, and GIF formats.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedCharacters` | [Aspose.OCR.CharactersAllowedType](https://reference.aspose.com/ocr/net/aspose.ocr/charactersallowedtype/) | `Aspose.OCR.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/net/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`AutoSkew` | boolean | `true` | Automatically [correct image tilt (deskew)](/ocr/net/deskew/) before proceeding to recognition.
`IgnoredCharacters` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`PreprocessingFilters` | [Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) | _none_ | Apply [image processing filters](/ocr/net/image-preprocessing/) that enhance an image before it is sent to the OCR engine.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.
`UpscaleSmallFont` | boolean | `false` | Improve small font recognition and detection of dense lines.

## Applicable to

- [Extracting text from receipts](/ocr/net/recognition/receipt/)

## Example

The following code example shows how to fine-tune receipt recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.ReceiptRecognitionSettings recognitionSettings = new Aspose.OCR.ReceiptRecognitionSettings();
recognitionSettings.AutoSkew = true;
recognitionSettings.Language = Aspose.OCR.Language.Latin;
recognitionSettings.ThreadsCount = 2;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeReceipt("receipt.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```