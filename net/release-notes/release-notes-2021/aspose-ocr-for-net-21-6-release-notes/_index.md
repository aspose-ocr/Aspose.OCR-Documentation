---
title: Aspose.OCR for .NET 21.6 - Release Notes
type: docs
weight: 7
url: /net/aspose-ocr-for-net-21-6-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.OCR for .NET 21.6

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 21.6.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRNET-359| Import new models (DSR, Chinese OCR) |Enhancement|
|OCRNET-360| Add method CalcSkewImage(uri) |Enhancement|


## Enhancements

- new ML model with improved regions recognition
- added Chinese language support
- added new Api method CalculateSkewFromUri(uri)


## Public API and Backwards Incompatible Changes

### New API

-  added method: double CalcSkewImageFromUri(String uri)

### Removed APIs

-  

### Will be deprecated

-

## Usage Example for Chinese text recognition and image angle calculation

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
            string image = "D://chinese.png";

            // Recognize chinese text           
            RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings{ Language = Language.Chi });

            // Save result		
            result.Save("D://test.txt", SaveFormat.Text);

			// Get the angle of the image from the URI
			float skew = api.CalculateSkewFromUri("https://blog.udemy.com/wp-content/uploads/2014/01/cssresult.png");
			Console.WriteLine($"Angle: {skew}");
        }
    }
}
	
{{< /highlight >}}
