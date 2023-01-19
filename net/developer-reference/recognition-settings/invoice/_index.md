---
weight: 70
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-invoice/
title: Invoice recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from invoice images.
keywords:
- setting
- config
- parameter
- image
- photo
- invoice
- bill
---

Aspose.OCR for .NET allows for very flexible customization of invoice recognition accuracy, performance, and other settings by configuring the properties of the [`InvoiceRecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/invoicerecognitionsettings/) object.

These settings are specifically tailored for processing scanned or photographed invoices.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedCharacters` | [Aspose.OCR.CharactersAllowedType](https://reference.aspose.com/ocr/net/aspose.ocr/charactersallowedtype/) | `Aspose.OCR.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/net/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`AutoSkew` | boolean | `true` | Automatically [correct image tilt (deskew)](/ocr/net/deskew/) before proceeding to recognition.
`IgnoredCharacters` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`PreprocessingFilters` | [Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) | _none_ | Apply [image processing filters](/ocr/net/image-preprocessing/) that enhance an image before it is sent to the OCR engine.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.

## Applicable to

- [Extracting text from an invoice](/ocr/net/recognition/invoice/)

## Example

The following code example shows how to fine-tune invoice recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.InvoiceRecognitionSettings InvoiceRecognitionSettings = new Aspose.OCR.InvoiceRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
recognitionSettings.AutoSkew = false;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeInvoice("invoice.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
