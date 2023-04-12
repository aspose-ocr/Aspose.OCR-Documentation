---
weight: 10
date: "2023-04-07"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-common/
aliases:
- /net/recognition-settings-image/
- /net/recognition-settings-document/
feedback: OCRNET
title: Common recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from images, scanned PDFs, DjVu files and other content.
keywords:
- setting
- config
- parameter
- image
- picture
- raster
- pdf
- document
- djvu
- pages
---

Aspose.OCR for .NET allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`RecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) object.

These universal settings are applicable when extracting text from single-page and multi-page images, scanned PDFs, DjVu files, folders, archives and other content.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedSymbols` | `string` | _All characters of the selected language_ | The [whitelist](/ocr/net/characters-whitelist/) of characters Aspose.OCR engine will look for.
`DetectAreasMode` | [Aspose.OCR.DetectAreasMode](https://reference.aspose.com/ocr/net/aspose.ocr/detectareasmode/) | _auto_ | Manually override the default [document areas detection method](/ocr/net/areas-detection/#area-detection-modes).
`IgnoredSymbols` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`LinesFiltration` | boolean | `false` | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`RecognitionAreas` | [List\<Aspose.Drawing.Rectangle\>](https://reference.aspose.com/pdf/net/aspose.pdf.drawing/rectangle/) | _entire image_ | List of [areas of the image](/ocr/net/image-regions-extract/) from which to extract text.
`RecognizeSingleLine` | boolean | `false` | Recognize a [single-line](/ocr/net/recognize-single-line/) image. Disables automatic document region detection.<br />Improves the recognition performance of simple images.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.
`UpscaleSmallFont` | boolean | `false` | Improve small font recognition and detection of dense lines.

{{% alert color="caution" %}}
**Upgrading from previous versions**

Starting with Aspose.OCR for .NET 23.3.1, these recognition settings are used as a universal replacement for image recognition settings (`RecognitionSettings`) and multi-page document recognition settings (`DocumentRecognitionSettings`).
{{% /alert %}}

## Applicable to

- [Extracting](/ocr/net/recognition/) text from images, scanned PDFs, DjVu files and other content provided as [`OcrInput` object](/ocr/net/ocrinput/).

## Example

The following code example shows how to fine-tune recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Customize recognition settings
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Ukr;
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.TABLE;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
