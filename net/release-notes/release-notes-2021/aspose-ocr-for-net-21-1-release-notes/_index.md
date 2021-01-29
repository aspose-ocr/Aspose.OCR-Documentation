---
title: Aspose.OCR for .NET 21.1 - Release Notes
type: docs
weight: 4
url: /net/aspose-ocr-for-net-21-1-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.OCR for .NET 21.1

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 21.1.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRNET-314|Optimize memory usage |Enhancement|
|OCRNET-315|Increase recognition quality |Enhancement|
|OCRNET-316|Implement Markdown and Searchable PDF results formats for download |Enhancement|


## Enhancements

- added ability to save the recognition result in the Markdown and Searchable PDF Document format
- added custom image quality correction with parameter TresholdValue
- improved performance and reduced memory costs


## Public API and Backwards Incompatible Changes

### New API

-  added property TresholdValue to the RecognitionSettings class

### Removed APIs

All methods of the previous release are supported.

### Will be deprecated

string RecognizeImage(MemoryStream stream, Rectangle rect);

string RecognizeImage(string fullPath, Rectangle rect);

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
            string image = "D://img.png";

            // Recognize image           
            RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings
                       {
                                 TresholdValue = 160
                       });

            // Save result

			Console.WriteLine(result.RecognitionText);
			
            result.Save("D://test.pdf", SaveFormat.Pdf);
            result.Save("D://test.md", SaveFormat.Md);
        }
    }
}

{{< /highlight >}}
