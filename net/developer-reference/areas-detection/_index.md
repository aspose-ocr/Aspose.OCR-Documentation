---
weight: 60
date: "2023-10-12"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/
feedback: OCRNET
aliases:
- /net/detect-areas-mode/
- /net/perform-ocr-with-mode-for-text-area-detectionn/
title:  Document areas detection
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

A scanned image or photograph of a text document may contain a large number of blocks of various content - text paragraphs, tables, illustrations, formulas, and the like. Detecting, ordering, and classifying areas of interest on a page is the cornerstone of successful and accurate OCR. This process is called _document areas detection_.

![Document structure analysis and recognition](structure-analysis.png)

Aspose.OCR offers several document areas detection algorithms, allowing you to choose the one that works best for your specific content.

## Area detection modes

You can manually override the default document areas detection method if you are unhappy with the results or get unwanted artifacts.

Document structure analysis algorithm is specified in an optional [`DetectAreasMode`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/detectareasmode/) parameter of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/).

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.DOCUMENT;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

Aspose.OCR for .NET supports the following document structure analysis methods provided in `DetectAreasMode` enumeration:

Name              | Value | Description | Use cases
----------------- | :---: | ----------- | ---------
`DetectAreasMode.NONE` | 0 | Do not analyze document structure. | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`DetectAreasMode.DOCUMENT` | 1 | Detect large blocks of text, such as paragraphs and columns. Optimal for multi-column documents with illustrations.<br />See [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers<br />High-quality scans
`DetectAreasMode.PHOTO` | 2 | Finds small text blocks inside complex images.<br />See [**DetectAreasMode.PHOTO**](/ocr/net/areas-detection/photo/) for additional details. | Driver’s licenses<br />Social security cards<br />Government and work IDs<br />Visas<br />Photos<br />Screenshots<br />Advertisements
`DetectAreasMode.COMBINE` | 3 | The combination of _DetectAreasMode.DOCUMENT_ and _DetectAreasMode.PHOTO_.<br />See [**DetectAreasMode.COMBINE**](/ocr/net/areas-detection/combine/) for additional details. | Posters<br />Billboards<br />Datasheets<br />Random photos<br />Batch recognition
`DetectAreasMode.TABLE` | 4 | Detects cells in tabular structures.<br />See [**DetectAreasMode.TABLE**](/ocr/net/areas-detection/table/) for additional details. | Tables<br />Invoices
`DetectAreasMode.CURVED_TEXT` | 5 | Auto-straightens curved lines and finds text blocks inside the resulting image.<br />See [**DetectAreasMode.CURVED_TEXT**](/ocr/net/areas-detection/curved_text/) for additional details. | Photos of books, magazine articles, and other curved pages.
`DetectAreasMode.TEXT_IN_WILD` | 6 | Finds individual words on images with sparse text and colored backgrounds.<br />See [**DetectAreasMode.TEXT_IN_WILD**](/ocr/net/areas-detection/text-in-wild/) for additional details. | Street photos<br />Price tags<br />Food labels<br />Menus<br />Catalogs<br />Ads
