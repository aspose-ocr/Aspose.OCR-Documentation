---
weight: 60
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/detect-areas-mode/
- /net/perform-ocr-with-mode-for-text-area-detectionn/
title:  Content areas detection
description: How Aspose.OCR identifies and analyzes the structure and layout of the image during recognition.
keywords:
- structure
- region
- area
- blocks
- neural network
- algorithm
- mode
---

A scanned image or photograph of a text document may contain a large number of blocks of various content - text paragraphs, tables, illustrations, formulas, and the like. Detecting, ordering, and classifying areas of interest on a page is the cornerstone of successful and accurate OCR. This process is called _content areas detection_.

![Document structure analysis and recognition](structure-analysis.png)

Aspose.OCR offers several content areas detection algorithms, allowing you to choose the one that works best for your specific content.

## Area detection modes

You can manually override the default content areas detection method if you are unhappy with the results or get unwanted artifacts.

Document structure analysis algorithm is specified in an optional [`DetectAreasMode`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/detectareasmode/) parameter of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/).

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set content areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.MULTICOLUMN;
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

Aspose.OCR for .NET supports the following document structure analysis methods provided in `DetectAreasMode` enumeration:

Name              | Description | Use cases
----------------- | ----------- | ---------
`DetectAreasMode.UNIVERSAL` | Detects all blocks of text in the image, including sparse and irregular text on street photos. Used by default.<br />See [**DetectAreasMode.UNIVERSAL**](/ocr/net/areas-detection/universal/) for additional details. | Photos<br />Screenshots<br />Advertisements<br />Datasheets<br />Street photos<br />Price tags<br />Food labels
`DetectAreasMode.MULTICOLUMN` | Detects large blocks of text formatted in several columns.<br />See [**DetectAreasMode.MULTICOLUMN**](/ocr/net/areas-detection/multicolumn/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers
`DetectAreasMode.LEAN` | Do not analyze document structure. Prioritizes speed and reduces resource consumption by omitting support for complex layouts. | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`DetectAreasMode.TABLE` | Detects cells in tabular structures.<br />See [**DetectAreasMode.TABLE**](/ocr/net/areas-detection/table/) for additional details. | Tables<br />Invoices
`DetectAreasMode.CURVED_TEXT` | Auto-straightens curved lines and finds text blocks inside the resulting image.<br />See [**DetectAreasMode.CURVED_TEXT**](/ocr/net/areas-detection/curved_text/) for additional details. | Photos of books, magazine articles, and other curved pages.
