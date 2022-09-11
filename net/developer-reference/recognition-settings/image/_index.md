---
weight: 10
date: "2022-09-07"
author: "Vladimir Lapin"
type: docs
url: /net/recognition-settings-image/
aliases:
- /net/recognition-settings/
title: Image recognition settings
description: Configuring Aspose.OCR for .NET recognition engine for extracting text from images.
keywords:
- setting
- config
- parameter
- image
- picture
- raster
---

Aspose.OCR for .NET allows for very flexible customization of recognition accuracy, performance, and other settings by configuring the properties of the [`RecognitionSettings`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) object.

These settings are applicable when extracting text from single-page raster images in JPEG, PNG, TIFF, BMP, and GIF formats.

Setting | Type | Default value | Description
------- | ---- | ------------- | -----------
`AllowedCharacters` | [Aspose.OCR.CharactersAllowedType](https://reference.aspose.com/ocr/net/aspose.ocr/charactersallowedtype/) | `Aspose.OCR.CharactersAllowedType.ALL` | The [predefined whitelist](/ocr/net/characters-whitelist/#predefined-character-sets) of characters Aspose.OCR engine will look for.
`AutoContrast` | boolean | `false` | Automatically [increase the contrast](/ocr/net/contrast/) of images before proceeding to recognition.
`AutoDenoising` | boolean | `false` | Automatically [remove noise](/ocr/net/denoise/) from images before proceeding to recognition.
`AutoSkew` | boolean | `true` | Automatically [correct image tilt (deskew)](/ocr/net/deskew/) before proceeding to recognition.
`DetectAreas` | boolean | `true` | Automatically select the optimal [areas detection algorithm](/ocr/net/areas-detection/) that suits the most common use cases.
`DetectAreasMode` | [Aspose.OCR.DetectAreasMode](https://reference.aspose.com/ocr/net/aspose.ocr/detectareasmode/) | _auto_ | Manually override the default [document areas detection method](/ocr/net/areas-detection/#area-detection-modes).
`IgnoredCharacters` | string | _none_ | A [blacklist](/ocr/net/characters-blacklist/) of characters that are ignored during recognition.
`Language` | [Aspose.OCR.Language](https://reference.aspose.com/ocr/net/aspose.ocr/language/) | `Aspose.OCR.Language.None` | Specify a [language](/ocr/net/languages/) for recognition.
`LinesFiltration` | boolean | `false` | Set to `true` to recognize text in tables.<br />Set to `false` to improve performance by ignoring table structures and treating tables as plain text.
`PreprocessingFilters` | [Aspose.OCR.Models.PreprocessingFilters.PreprocessingFilter](https://reference.aspose.com/ocr/net/aspose.ocr.models.preprocessingfilters/preprocessingfilter/) | _none_ | Apply [image processing filters](/ocr/net/image-preprocessing/) that enhance an image before it is sent to the OCR engine.
`RecognitionAreas` | [List\<Aspose.Drawing.Rectangle\>](https://reference.aspose.com/pdf/net/aspose.pdf.drawing/rectangle/) | _entire image_ | List of [areas of the image](/ocr/net/image-regions-extract/) from which to extract text.
`RecognizeSingleLine` | boolean | `false` | Recognize a [single-line](/ocr/net/recognize-single-line/) image. Disables automatic document region detection.<br />Improves the recognition performance of simple images.
`SkewAngle` | float | `0` | Manually [rotate](/ocr/net/deskew/#manual-skew-correction) the image by the specified degree.
`ThreadsCount` | integer | _auto_ | The number of [CPU threads](/ocr/net/multithreading/) used for recognition.
`ThresholdValue` | integer | _auto_ | [Override](/ocr/net/binarization/#using-binarization-threshold) the automatic binarization settings.

## Applicable to

- [Extracting text from a raster image](/ocr/net/recognition/image/)
- [Extracting text from pixel array](/ocr/net/recognition/pixel/)
- [Extracting text from URL](/ocr/net/recognition/url/)

## Example

The following code example shows how to fine-tune recognition:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AllowedCharacters = Aspose.OCR.CharactersAllowedType.LATIN_ALPHABET;
recognitionSettings.AutoDenoising = true;
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.TABLE;
recognitionSettings.SkewAngle = 90;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
