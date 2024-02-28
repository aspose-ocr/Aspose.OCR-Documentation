---
weight: 60
date: "2024-02-27"
author: "Vladimir Lapin"
type: docs
url: /net/areas-detection/text-in-wild/
feedback: OCRNET
title:  DetectAreasMode.TEXT_IN_WILD
description: How Aspose.OCR finds words on an image using the DetectAreasMode.TEXT_IN_WILD algorithm.
keywords:
- structure
- region
- area
- photo
- street
---

{{% alert color="caution" %}} 
To use this structure detection algorithm, [install](/ocr/net/modules/) sparse text recognition model (**aspose-ocr-text-in-wild-v1**) in your project.
{{% /alert %}}

When this mode is enabled, Aspose.OCR engine finds individual words on images with sparse text. It is very effective when dealing with the following images:

- Street photos.
- Road signs.
- Signboards.
- Price tags.
- Food labels, nutritional information, ingredient lists.
- Menus.
- Catalogs.

This algorithm automatically activates detection of the coordinates of image regions containing [words](/ocr/net/image-regions-word-find/). There is no need to use [Aspose.OCR.AsposeOcr.DetectRectangles](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/detectrectangles/) method.

![Text-in-wild structure detection algorithm](label-regions.png)

However, this algorithm is very inefficient when dealing with large amounts of text, such as pages from books and newspaper articles. Try [**DetectAreasMode.DOCUMENT**](/ocr/net/areas-detection/document/) instead.

## Example

The following code sample demonstrates how to use this document areas detection algorithm:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Set document areas detection mode
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
recognitionSettings.DetectAreasMode = Aspose.OCR.DetectAreasMode.TEXT_IN_WILD;
// Recognize image
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.Recognize(input, recognitionSettings);
Console.WriteLine(result[0].RecognitionText);
```

## Limitations

The algorithm only works with Latin letters and numbers. You cannot specify the [recognition language](/ocr/net/languages/) and provide [whitelisted/blacklisted characters](/ocr/net/recognition-settings-common/). 
