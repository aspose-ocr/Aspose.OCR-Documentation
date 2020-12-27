---
title: Aspose.OCR for .NET 20.12 - Release Notes
type: docs
weight: 4
url: /net/aspose-ocr-for-net-20-12-release-notes/
---

{{% alert color="primary" %}}

This page contains release notes information for Aspose.OCR for .NET 20.12

{{% /alert %}}

{{% alert color="primary" %}}

**GPU version: 20.12.0**

{{% /alert %}}

## All Features

|Key|Summary|Category|
|---|---|---|
|OCRNET-290|Implement the possibility to get result in .doc, .docx, .odt and .txt formats |Enhancement|


## Enhancements

- added ability to save the recognition result in the plain text, Microsoft Word, Office Open XML or ODF Text Document format

## Public API and Backwards Incompatible Changes

### New API

-  added method Save to the RecognitionResult object

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
            RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings());

            // Save result

            result.Save("D://test.docx", SaveFormat.Docx);
            result.Save("D://test.doc", SaveFormat.Doc);
            result.Save("D://test.odt", SaveFormat.Odt);
            result.Save("D://test.txt", SaveFormat.Text);
        }
    }
}

{{< /highlight >}}
