---
weight: 1
date: "2023-07-25"
author: "Vladimir Lapin"
type: docs
url: /net/release-notes/latest/
feedback: OCRNET
title: Latest release (July 2023)
description: A summary of recent changes, enhancements and bug fixes in Aspose.OCR for .NET 23.7.1 (July 2023) release.
keywords:
- latest
- new
- release
- changelog
---

{{% alert color="primary" %}}
This article contains a summary of recent changes, enhancements and bug fixes in [**Aspose.OCR for .NET 23.7.1 (July 2023)**](https://www.nuget.org/packages/Aspose.OCR/23.7.1) release.

GPU version: **23.5.0**
{{% /alert %}}

## Deprecation warning

{{% alert color="caution" %}}
The [release 23.3.1](/ocr/net/aspose-ocr-for-net-23-3-1-release-notes/) introduced a slimmer, faster and more straightforward API. All of your existing code will continue to work and you can even make minor updates to it, but be aware that all deprecated elements are scheduled to be removed in release **23.11.0 (November 2023)** in favor of the new API.

**Time to deprecation: 3 months left.**
{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRNET&#8209;708 | Added new recognition settings for automatic handling of white text on a dark/black background.<br />See [**Added public APIs**](#added-public-apis) for important details. | New feature

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for .NET 23.7.1** that may affect the code of existing applications.

### Added public APIs:

The following public APIs have been introduced in **Aspose.OCR for .NET 23.7.1** release:

#### `Aspose.OCR.RecognitionSettings.AutomaticColorInversion`

When set to `true`, Aspose.OCR for .NET uses a special OCR algorithm for automatic detection and accurate recognition of of white text on a dark/black background.

{{% alert color="primary" %}}
Unless you are optimizing every aspect of recognition (for example, for online applications or entry-level devices), do not disable this setting.
{{% /alert %}}

This setting is applicable when using one of the following [document area detection modes](/ocr/net/areas-detection/):

- [`DetectAreasMode.PHOTO`](/ocr/net/areas-detection/photo/)
- [`DetectAreasMode.COMBINE`](/ocr/net/areas-detection/combine/)
- [`DetectAreasMode.TABLE`](/ocr/net/areas-detection/table/)
- [`DetectAreasMode.CURVED_TEXT`](/ocr/net/areas-detection/curved_text/)

#### `Aspose.OCR.ReceiptRecognitionSettings.AutomaticColorInversion`

When set to `true`, Aspose.OCR for .NET uses a special OCR algorithm for automatic detection and accurate recognition of of white text on a dark/black background in scanned or photographed receipts.

{{% alert color="primary" %}}
Unless you are optimizing every aspect of recognition (for example, for online applications or entry-level devices), do not disable this setting.
{{% /alert %}}

#### `Aspose.OCR.IDCardRecognitionSettings.AutomaticColorInversion`

When set to `true`, Aspose.OCR for .NET uses a special OCR algorithm for automatic detection and accurate recognition of of white text on a dark/black background in scanned or photographed ID cards.

{{% alert color="primary" %}}
Unless you are optimizing every aspect of recognition (for example, for online applications or entry-level devices), do not disable this setting.
{{% /alert %}}

#### `Aspose.OCR.PassportRecognitionSettings.AutomaticColorInversion`

When set to `true`, Aspose.OCR for .NET uses a special OCR algorithm for automatic detection and accurate recognition of of white text on a dark/black background in scanned or photographed passports.

{{% alert color="primary" %}}
Unless you are optimizing every aspect of recognition (for example, for online applications or entry-level devices), do not disable this setting.
{{% /alert %}}

#### `Aspose.OCR.CarPlateRecognitionSettings.AutomaticColorInversion`

When set to `true`, Aspose.OCR for .NET uses a special OCR algorithm for automatic detection and accurate recognition of of white text on a dark/black background in photographed vehicle license plates.

{{% alert color="primary" %}}
Unless you are optimizing every aspect of recognition (for example, for online applications or entry-level devices), do not disable this setting.
{{% /alert %}}

#### `Aspose.OCR.InvoiceRecognitionSettings.AutomaticColorInversion`

When set to `true`, Aspose.OCR for .NET uses a special OCR algorithm for automatic detection and accurate recognition of of white text on a dark/black background in scanned or photographed invoices.

{{% alert color="primary" %}}
Unless you are optimizing every aspect of recognition (for example, for online applications or entry-level devices), do not disable this setting.
{{% /alert %}}

### Updated public APIs:

_No changes_

### Removed public APIs:

_No changes._

## Examples

The examples below illustrates the changes introduced in this release:

### Automatic handling of inverted texts

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Apply inverted text detection
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.AutomaticColorInversion = true;
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.TABLE;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
Console.WriteLine(result[0].RecognitionText);
```
