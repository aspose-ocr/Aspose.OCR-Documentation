---
weight: 40
date: "2024-03-01"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/table/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
title:  DetectAreasMode.TABLE
description: How Aspose.OCR determines the structure of a document using the DetectAreasMode.TABLE algorithm.
keywords:
- structure
- region
- area
- table
- cell
- row
---

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/net/modules/) advanced OCR models (**aspose-ocr-advanced-recognition-v1**) in your project.
{{% /alert %}}

When this mode is enabled, OCR engine detects tabular structures on an image and extracts text from cells. This areas detection mode is recommended when working with scanned spreadsheets, financial and accounting reports, invoices, and other tables.

However, this algorithm is inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.TABLE;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
