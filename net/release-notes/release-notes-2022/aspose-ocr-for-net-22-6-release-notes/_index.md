---
title: Aspose.OCR for .NET 22.6 - Release Notes
type: docs
weight: 127
url: /net/aspose-ocr-for-net-22-6-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.OCR for .NET 22.6

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 21.6.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRNET-535|Integrate pre and post processing algorithms for Binarization neural network |Enhancement|
|OCRNET-517|Integrate Binarization neural network + tests |Enhancement|
|OCRNET-465|Remove dependence from System.Drawing and try to use Aspose.Drawing |Enhancement|
|OCRNET-513|Table recognition |Enhancement|

## Enhancements

- added new ML model Binarization and auto_denoising settings
- removed System.Drawing dependency and added Aspose.Drawing
- added Table recognition


## Public API and Backwards Incompatible Changes

### New API

- added property AutoDenoising to the RecognitionSettings class
- added TABLE value to the DetectAreasMode enum

### Removed APIs

All methods of the previous release are supported.

### Will be deprecated

-

## Usage Example

{{< highlight csharp >}}


using Aspose.OCR;

namespace ProgramOCR
{
    class Program
    {
        static void Main(string[] args)
        {
            // Get API
            AsposeOcr api = new AsposeOcr();

            // Create license
            License lic = new License();

            // Set license 
            lic.SetLicense("Aspose.Total.lic");

            // Get image for recognize
            string image = "img.jpg";

            // Recognize image with pre- processing  
			RecognitioResult result = api.RecognizeImage(image, new RecognitionSettings { AutoDenoising = false});
			
			// Print result
			Console.WriteLine(result.RecognitionText);
			
			
			 // Get image with table structure for recognize
            string table = "table.jpg";

            // Recognize table
			RecognitioResult resultTable = api.RecognizeImage(table, new RecognitionSettings { DetectAreasMode = DetectAreasMode.TABLE});
			
			// Print result
			Console.WriteLine(resultTable.RecognitionText);
        }
    }
}

{{< /highlight >}}
