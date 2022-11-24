---
weight: 50
date: "2022-09-28"
author: "Vladimir Lapin"
type: docs
url: /java/areas-detection/
aliases:
- /java/detect-areas-mode/
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

If you call [`setDetectAreas(true)`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setDetectAreas-boolean-) method of [recognition settings](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings), Aspose.OCR automatically selects the optimal areas detection algorithm that suits the most common use cases.

Document areas detection uses a neural network, which requires additional time and resources on the computer running the application. You can disable it (call `setDetectAreas(false)`) when extracting single-line texts, or working with very simple documents without formatting and pictures. This can improve the performance of your application, especially when integrating OCR functionality into web sites and public APIs with minimal impact on the quality of recognition results.

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Enable automatic document areas detection
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setAllowedCharacters(CharactersAllowedType.LATIN_ALPHABET);
recognitionSettings.setDetectAreas(true);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```

{{% alert color="primary" %}} 
Never disable automatic document areas detection when working with multi-paragraph and multi-column documents, tables, or photos. This can significantly reduce recognition accuracy.
{{% /alert %}}

## Area detection modes

You can manually override the default document areas detection method if you are unhappy with the results or get unwanted artifacts.

Document structure analysis algorithm is specified using [`setDetectAreasMode`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setDetectAreasMode-com.aspose.ocr.DetectAreasMode-) method of [recognition settings](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings).

```java
// Create instance of OCR API
AsposeOCR api = new AsposeOCR();
// Enable automatic document areas detection
RecognitionSettings recognitionSettings = new RecognitionSettings();
recognitionSettings.setDetectAreasMode(DetectAreasMode.DOCUMENT);
// Extract text from image
RecognitionResult result = api.RecognizePage("source.png", recognitionSettings);
System.out.println("Recognition result:\n" + result.recognitionText + "\n\n");
```

Aspose.OCR for Java supports the following [document structure analysis](/ocr/structure-analysis/) methods provided in [`DetectAreasMode`] enumeration:

Name              | Value | Description | Use cases
----------------- | :---: | ----------- | ---------
`DetectAreasMode.NONE` | 0 | Do not analyze document structure. Similar to calling [`setDetectAreas(false)`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setDetectAreas-boolean-) method of [recognition settings](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings). | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`DetectAreasMode.DOCUMENT` | 1 | Detect large blocks of text, such as paragraphs and columns. Optimal for multi-column documents with illustrations.<br />See [**DetectAreasMode.DOCUMENT**](/ocr/java/areas-detection/document/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers<br />High-quality scans
`DetectAreasMode.PHOTO` | 2 | Finds small text blocks inside complex images.<br />See [**DetectAreasMode.PHOTO**](/ocr/java/areas-detection/photo/) for additional details. | Driver’s licenses<br />Social security cards<br />Government and work IDs<br />Visas<br />Photos<br />Screenshots<br />Advertisements
`DetectAreasMode.COMBINE` | 3 | The combination of _DetectAreasMode.DOCUMENT_ and _DetectAreasMode.PHOTO_.<br />See [**DetectAreasMode.COMBINE**](/ocr/java/areas-detection/combine/) for additional details. | Posters<br />Billboards<br />Datasheets<br />Random photos<br />Batch recognition
`DetectAreasMode.TABLE` | 4 | Detects cells in tabular structures.<br />See [**DetectAreasMode.TABLE**](/ocr/java/areas-detection/table/) for additional details. | Tables<br />Invoices
`DetectAreasMode.CURVED_TEXT` | 5 | Auto-straightens curved lines and finds text blocks inside the resulting image.<br />See [**DetectAreasMode.CURVED_TEXT**](/ocr/java/areas-detection/curved_text/) for additional details. | Photos of books, magazine articles, and other curved pages.
