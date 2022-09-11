---
weight: 20
date: "2022-09-07"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-document/
title: Multi-page document recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from multi-page images and PDF documents.
keywords:
- setting
- config
- parameter
- pdf
- document
- djvu
- pages
---

Aspose.OCR for .NET allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`DocumentRecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/documentrecognitionsettings/) object.

These settings are applicable when extracting text from multi-page images in TIFF and DjVu format, as well as scanned PDF documents.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedCharacters` | [Aspose.OCR.CharactersAllowedType](https://reference.aspose.com/ocr/net/aspose.ocr/charactersallowedtype/) | `Aspose.OCR.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/net/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`AutoContrast` | boolean | `false` | Automatically [increase the contrast](/ocr/net/contrast/) of pages before proceeding to recognition.
`AutoDenoising` | boolean | `false` | Automatically [remove noise](/ocr/net/denoise/) from pages before proceeding to recognition.
`AutoSkew` | boolean | `true` | Automatically [correct page tilt (deskew)](/ocr/net/deskew/) before proceeding to recognition.
`DetectAreas` | boolean | `true` | Automatically select the optimal [areas detection algorithm](/ocr/net/areas-detection/) that suits the most common use cases.
`DetectAreasMode` | [Aspose.OCR.DetectAreasMode](https://reference.aspose.com/ocr/net/aspose.ocr/detectareasmode/) | _auto_ | Manually override the default [document areas detection method](/ocr/net/areas-detection/#area-detection-modes).
`IgnoredCharacters` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`LinesFiltration` | boolean | `false` | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`PagesNumber` | integer | `1` | The number of pages to be recognized in a multi-page file.
`PreprocessingFilters` | [Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) | _none_ | Apply [image processing filters](/ocr/net/image-preprocessing/) that enhance pages before they are sent to the OCR engine.
`RecognizeSingleLine` | boolean | `false` | Recognize a [single line](/ocr/net/recognize-single-line/) image. Disables automatic document region detection.<br />Improves the recognition performance of simple images.
`SkewAngle` | float | `0` | Manually [rotate](/ocr/net/deskew/#manual-skew-correction) the image by the specified degree.
`StartPage` | integer | `0` | The page number from which to start recognition of the multi-page file. First page number is `0`.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.
`ThresholdValue` | integer | _auto_ | [Override](/ocr/net/binarization/#using-binarization-threshold) the automatic binarization settings.

## Applicable to

- [Extracting text from PDF document](/ocr/net/recognition/pdf/)
- [Extracting text from multi-page TIFF](/ocr/net/recognition/tiff/)
- [Extracting text from multi-page DjVu](/ocr/net/recognition/djvu/)

## Example

The following code example shows how to fine-tune recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.DocumentRecognitionSettings recognitionSettings = new Aspose.OCR.DocumentRecognitionSettings();
recognitionSettings.StartPage = 3;
recognitionSettings.PagesNumber = 10;
recognitionSettings.Language = Aspose.OCR.Language.Spa;
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizePdf("source.pdf", recognitionSettings);
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.json", Aspose.OCR.SaveFormat.Json, results);
```
