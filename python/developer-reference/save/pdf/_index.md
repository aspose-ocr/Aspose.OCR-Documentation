---
weight: 20
date: "2024-10-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/save-searchable-pdf/
feedback: OCRPYNET
title: Saving recognition results as a searchable PDF
description: Saving Aspose.OCR for Python via .NET recognition results as a searchable and indexable PDF document.
keywords:
- save
- result
- file
- PDF
---

To convert recognition results into a searchable and indexable PDF document, use `save_multipage_document()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition. Provide `SaveFormat.PDF` as `save_format` parameter.

In addition to the recognized text, you can save the resulting PDF may have original images in the background and a transparent text overlay that can be searched, selected and copied. The type of the PDF document is controlled by the selected result type option:

Format | Description
------ | -----------
`SaveFormat.PDF` | The original images are placed in the background; the recognized text is placed as an invisible but searchable and selectable overlay on top of the images. Can be useful if you need to keep all notes, images, marks and other data along with the text.
`SaveFormat.PDF_NO_IMG` | The PDF document containing only the recognized text. The original images are not saved along with the recognition results. This can be useful when digitizing large amounts of high-quality text (such as books) so that the resulting file takes up much less space than using the `SaveFormat.PDF` parameter.

To balance between file size and image quality of saved PDFs, use the optional `optimizePdf` parameter, which accepts the value of `PdfOptimizationMode` enumeration.

Name              | Description
----------------- | -----------
`NONE`            | Do not optimize PDF size.
`MAXIMUM_QUALITY` | **Default.** Optimize file size while preserving the highest image quality.
`HIGH_QUALITY`    | Smaller PDF file size at the expense of sight image downsampling.
`BALANCED`        | Downsample images to balance file size and image quality.
`AGGRESSIVE`      | Significantly reduce the PDF file size at the expense of lower image quality.

{{% alert color="primary" %}}
The resulting PDF file size depends on the size and complexity of the original image.
{{% /alert %}}

You can optionally enable [automatic spelling corrections](/ocr/python-net/automatic-spelling-correction/) for recognition results, provide a [custom dictionary](/ocr/python-net/dictionaries/), or specify the font to be embedded into a PDF document. The latter is only applicable when saving recognition results into text-only PDF (`SaveFormat.PDF_NO_IMG`).

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.PDF)
input.add("source.pdf")
# Recognize the image
results = api.recognize(input)
# Save recognition result
save_multipage_document("result.pdf", SaveFormat.PDF, results)
```
