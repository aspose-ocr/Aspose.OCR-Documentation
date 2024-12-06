---
weight: 60
date: "2023-07-25"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-receipt/
feedback: OCRNET
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
`AllowedSymbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`IgnoredSymbols` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.
`UpscaleSmallFont` | boolean | `false` | Improve small font recognition and detection of dense lines.
`AutomaticColorInversion` | boolean | `true` | Improve recognition accuracy of white text on a dark/black background. If you are not optimizing every aspect of recognition (for example, for online applications or entry-level devices), leave this setting set to true.

## Applicable to

- [Extracting text from receipts](/ocr/net/recognition/receipt/)

## Example

The following code example shows how to fine-tune receipt recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("receipt1.png");
input.Add("receipt2.png");
// Recognition settings
Aspose.OCR.ReceiptRecognitionSettings recognitionSettings = new Aspose.OCR.ReceiptRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize receipts
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizeReceipt(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
