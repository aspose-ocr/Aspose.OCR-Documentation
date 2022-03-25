---
title: Aspose.OCR for .NET 22.1 - Release Notes
type: docs
weight: 120
url: /net/aspose-ocr-for-net-22-1-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.OCR for .NET 22.1

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 21.6.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRNET-456|Add multipage TIFF input support |Enhancement|


## Enhancements

- added ability torecognize multi-page TIFF images


## Public API and Backwards Incompatible Changes

### New API

-  added method List<RecognitionResult> RecognizeTiff(string fullPath, DocumentRecognitionSettings settings) to the AsposeOcr class

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
            string image = "D://img.tiff";

            // Recognize image           
            DocumentRecognitionSettings set = new DocumentRecognitionSettings();
            //set.PagesNumber = 0;// set as you need
            List<RecognitionResult> result = api.RecognizeTiff(imgPath, set);

            // Print result
			foreach (var item in result)            
			{
                Console.WriteLine(item.RecognitionText);
            }
        }
    }
}

{{< /highlight >}}
