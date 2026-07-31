---
weight: 52
date: "2026-07-31"
author: "Anna Pylaieva"
type: docs
url: /net/font-detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title: Font detection
description: How to detect font family, style, size, and confidence for recognized text lines.
keywords:
- font
- style
- size
- detect
- text line
---

Aspose.OCR for .NET can detect font information for each recognized text line. This is useful when you need to preserve visual characteristics of recognized content or analyze documents by typography.

Font detection is enabled through `RecognitionSettings.DetectFonts`. When the setting is enabled, each non-empty item in `RecognitionResult.RecognitionLinesResult` can contain a `FontLineResult` object in its `Font` property.

{{% alert color="primary" %}}
Font detection is designed for recognized text lines. Enable line-level recognition output and use clear, sufficiently large text images for best results.
{{% /alert %}}

## Font information

`FontLineResult` contains the following information:

Property | Type | Description
-------- | ---- | -----------
`LineIndex` | `int` | Zero-based line index in the processed font batch.
`SizePx` | `int` | Detected line height in pixels.
`SizePtEstimate` | `double?` | Estimated font size in points.
`Style` | `string` | Detected font style, for example `regular`, `italic`, or `bold_italic`.
`StyleConfidence` | `double` | Confidence score for the detected style.
`Font` | `string` | Detected font family name.
`FontConfidence` | `double` | Confidence score for the detected font family.

## Detecting fonts

Set `RecognitionSettings.DetectFonts` to `true`, recognize the image, and read the `Font` property of each recognized line.

```csharp
using Aspose.OCR;
using System;
using System.Linq;

AsposeOcr api = new AsposeOcr();

OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("source.png");

RecognitionSettings settings = new RecognitionSettings
{
	DetectFonts = true,
	DetectAreasMode = DetectAreasMode.LEAN,
	Language = Language.Latin,
	ThreadsCount = 1
};

RecognitionResult result = api.Recognize(input, settings)[0];

foreach (RecognitionResult.LinesResult line in result.RecognitionLinesResult
	.Where(line => !string.IsNullOrWhiteSpace(line.TextInLine)))
{
	FontLineResult font = line.Font;

	Console.WriteLine(line.TextInLine);
	Console.WriteLine($"Font: {font.Font} ({font.FontConfidence:P0})");
	Console.WriteLine($"Style: {font.Style} ({font.StyleConfidence:P0})");
	Console.WriteLine($"Size: {font.SizePx}px / {font.SizePtEstimate}pt");
}
```

## Processing multiple images

Font detection works with batches. Each `RecognitionResult` contains line-level font data for the corresponding input image or page.

```csharp
using Aspose.OCR;
using System;
using System.Linq;

AsposeOcr api = new AsposeOcr();

OcrInput input = new OcrInput(InputType.SingleImage);
input.Add("arial.png");
input.Add("calibri.png");

RecognitionSettings settings = new RecognitionSettings
{
	DetectFonts = true,
	DetectAreasMode = DetectAreasMode.LEAN,
	Language = Language.Latin,
	ThreadsCount = 1
};

foreach (RecognitionResult result in api.Recognize(input, settings))
{
	foreach (RecognitionResult.LinesResult line in result.RecognitionLinesResult
		.Where(line => !string.IsNullOrWhiteSpace(line.TextInLine)))
	{
		Console.WriteLine($"{line.TextInLine}: {line.Font.Font}, {line.Font.Style}");
	}
}
```
