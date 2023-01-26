---
weight: 72
date: "2022-06-30"
author: "Vladimir Lapin"
type: docs
url: /net/aspose-ocr-for-net-22-6-release-notes/
feedback: OCRNET
title: Aspose.OCR for .NET 22.6 - Release Notes
description: A summary of recent changes, enhancements and bug fixes in Aspose.OCR for .NET 22.6 (June 2022) release.
keywords:
- 2022
- June
- release
- changelog
---

{{% alert color="primary" %}}

This article contains a summary of recent changes, enhancements and bug fixes in [**Aspose.OCR for .NET 22.6 (June 2022)**](https://www.nuget.org/packages/Aspose.OCR/22.6.0) release.

GPU version: **21.6.0**

{{% /alert %}}

## What was changed

Key | Summary | Category
--- | ------- | --------
OCRNET-465 | Replaced **System.Drawing** with **Aspose.Drawing** to improve performance and cross-platform support. | Enhancement
OCRNET-513 | Added a new [detection mode](/ocr/net/detect-areas-mode/) for better identification and recognition of tabular structures. | Enhancement
OCRNET-517<br />OCRNET-535 | Added a new machine learning model for [image denoising](/ocr/net/denoising-correction/):<ul><li>Integrated Binarized Neural Network (BNN) and related tests.</li><li>Implemented pre- and post-processing algorithms for Binarized Neural Network.</li></ul> | New feature

## Public API changes and backwards compatibility

This section lists all public API changes introduced in **Aspose.OCR for .NET 22.6** that may affect the code of existing applications.

### Added public APIs:

The following public APIs have been introduced in this release.

#### RecognitionSettings.AutoDenoising

A new [recognition setting](/ocr/net/aspose.ocr/recognitionsettings/) for enabling or disabling automatic noise removal from recognized images.

{{% alert color="primary" %}}

When enabled, images are pre-processed by a specialized neural network to remove dirt, spots, scratches, glare, unwanted gradients, and other noise. It consumes additional resources and is disabled by default.

{{% /alert %}}

#### DetectAreasMode.TABLE

A new [DetectAreasMode](https://reference.aspose.com/ocr/net/aspose.ocr/detectareasmode/) value that allows to choose a neural network for the automatic detection of table cells.

### Updated public APIs:

_No changes._

### Removed public APIs:

_No changes._

## Usage examples

The examples below illustrates the changes introduced in this release:

### Recognize image with automatic noise removal

{{< highlight csharp >}}
using Aspose.OCR;

namespace ProgramOCR
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create instance of OCR API
            AsposeOcr api = new AsposeOcr();
            // Set license
            License lic = new License();
            lic.SetLicense("Aspose.Total.lic");
            // Image path
            string image = "noisy.jpg";
            // Recognize
            RecognitioResult result = api.RecognizeImage(image, new RecognitionSettings {AutoDenoising = false});
            //Print recognition results
            Console.WriteLine(result.RecognitionText);
        }
    }
}
{{< /highlight >}}

### Recognize image with tabular content

{{< highlight csharp >}}
using Aspose.OCR;

namespace ProgramOCR
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create instance of OCR API
            AsposeOcr api = new AsposeOcr();
            // Set license
            License lic = new License();
            lic.SetLicense("Aspose.Total.lic");
            // Image path
            string image = "table.jpg";
            // Recognize
            RecognitioResult resultTable = api.RecognizeImage(image, new RecognitionSettings {DetectAreasMode = DetectAreasMode.TABLE});
            //Print recognition results
            Console.WriteLine(resultTable.RecognitionText);
        }
    }
}
{{< /highlight >}}
