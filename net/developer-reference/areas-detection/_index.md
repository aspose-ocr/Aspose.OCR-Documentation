---
weight: 50
date: "2022-08-19"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/
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

## Automatic areas detection

If [`DetectAreas`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/detectareasmode/) parameter of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/) is enabled (set to `true`), Aspose.OCR automatically selects the optimal areas detection algorithm that suits the most common use cases.

Document areas detection uses a neural network, which requires additional time and resources on the computer running the application. You can disable it (set `DetectAreasMode` property to `false`) when extracting single-line texts, or working with very simple documents without formatting and pictures. This can improve the performance of your application, especially when integrating OCR functionality into web sites and public APIs with minimal impact on the quality of recognition results.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Enable automatic document areas detection
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreas = true;
// Recognize image
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```

{{% alert color="primary" %}} 
Never disable automatic document areas detection when working with multi-paragraph and multi-column documents, tables, or photos. This can significantly reduce recognition accuracy.
{{% /alert %}}

## Area detection modes

You can manually override the default document areas detection method if you are unhappy with the results or get unwanted artifacts.

Document structure analysis algorithm is specified in an optional [`DetectAreasMode`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/detectareasmode/) parameter of [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/).

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.DOCUMENT;
// Recognize image
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```

Aspose.OCR for .NET supports the following [document structure analysis](/ocr/structure-analysis/) methods provided in [`DetectAreasMode`] enumeration:

Name              | Value | Description | Use cases
----------------- | :---: | ----------- | ---------
`DetectAreasMode.NONE` | 0 | Do not analyze document structure. Similar to disabling [`DetectAreas`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/detectareasmode/) parameter in [recognition settings](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/). | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`DetectAreasMode.DOCUMENT` | 1 | Detect large blocks of text, such as paragraphs and columns. Optimal for multi-column documents with illustrations.<br />See [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers<br />High-quality scans
`DetectAreasMode.PHOTO` | 2 | Finds small text blocks inside complex images.<br />See [**DetectAreasMode.PHOTO**](/ocr/net/areas-detection/photo/) for additional details. | Driver’s licenses<br />Social security cards<br />Government and work IDs<br />Visas<br />Photos<br />Screenshots<br />Advertisements
`DetectAreasMode.COMBINE` | 3 | The combination of _DetectAreasMode.DOCUMENT_ and _DetectAreasMode.PHOTO_.<br />See [**DetectAreasMode.COMBINE**](/ocr/net/areas-detection/combine/) for additional details. | Posters<br />Billboards<br />Datasheets<br />Random photos<br />Batch recognition
`DetectAreasMode.TABLE` | 4 | Detects cells in tabular structures. | Tables<br />Invoices
