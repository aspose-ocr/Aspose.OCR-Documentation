---
weight: 11
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/save-searchable-pdf/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/save-ocr-result-as-multipage-document/
title: Saving recognition results as a searchable PDF
description: Saving Aspose.OCR for .NET recognition results as a searchable and indexable PDF document.
keywords:
- save
- result
- file
- PDF
---

To convert recognition results into a searchable and indexable PDF document, use `SaveMultipageDocument` method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition. Provide `Aspose.OCR.SaveFormat.Pdf` as `saveFormat` parameter.

In addition to the recognized text, you can save the resulting PDF may have original images in the background and a transparent text overlay that can be searched, selected and copied. The type of the PDF document is controlled by the selected result type option:

Format | Description
------ | -----------
`Aspose.OCR.SaveFormat.Pdf` | The original images are placed in the background; the recognized text is placed as an invisible but searchable and selectable overlay on top of the images. Can be useful if you need to keep all notes, images, marks and other data along with the text.
`Aspose.OCR.SaveFormat.PdfNoImg` | The PDF document containing only the recognized text. The original images are not saved along with the recognition results. This can be useful when digitizing large amounts of high-quality text (such as books) so that the resulting file takes up much less space than using the `Aspose.OCR.SaveFormat.Pdf` parameter.

{{% alert color="primary" %}}
When an original image is placed in the background, only the following processing filters are applied to the background image:

- [Skew correction](/ocr/net/deskew/) (including automatic deskewing and manual rotation).
- [Resizing](/ocr/net/resize/).

Other [image processing filters](/ocr/net/image-processing/) are applied during recognition, but do not affect the background image in a searchable PDF.
{{% /alert %}}

To balance between file size and image quality of saved PDFs, use the optional `optimizePdf` parameter, which accepts the value of `Aspose.OCR.PdfOptimizationMode` enumeration.

Name              | Value | Description
----------------- | ----- | -----------
`NONE`            | 0     | Do not optimize PDF size.
`MAXIMUM_QUALITY` | 1     | **Default.** Optimize file size while preserving the highest image quality.
`HIGH_QUALITY`    | 2     | Smaller PDF file size at the expense of sight image downsampling.
`BALANCED`        | 3     | Downsample images to balance file size and image quality.
`AGGRESSIVE`      | 4     | Significantly reduce the PDF file size at the expense of lower image quality.

{{% alert color="primary" %}}
The resulting PDF file size depends on the size and complexity of the original image.
{{% /alert %}}

You can optionally enable [automatic spelling corrections](/ocr/net/automatic-spelling-correction/) for recognition results, provide a [custom dictionary](/ocr/net/dictionaries/), or specify the font to be embedded into a PDF document. The latter is only applicable when saving recognition results into text-only PDF (`Aspose.OCR.SaveFormat.PdfNoImg`).

{{< tabs tabID="1" tabTotal="2" tabName1="Save PDF to file" tabName2="Write PDF to memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Save results
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("page1.png");
input.Add("page2.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Save results
using(MemoryStream ms = new MemoryStream())
{
	Aspose.OCR.AsposeOcr.SaveMultipageDocument(ms, Aspose.OCR.SaveFormat.Pdf, results);
}
```
{{< /tab >}}
{{< /tabs >}}
