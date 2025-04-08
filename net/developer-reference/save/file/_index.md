---
weight: 10
date: "2025-01-22"
author: "Vladimir Lapin"
type: docs
url: /net/save-file/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
aliases:
- /net/get-ocr-result-as-file/
- /net/get-ocr-result-as-stream/
title: Saving recognition results as a file
description: Saving Aspose.OCR for .NET recognition results as PDF, text, Word, or Excel documents, as well as XML and JSON files.
keywords:
- save
- result
- file
- Office
- Word
- Excel
- document
- spreadsheet,
- JSON,
- XML,
- text
- Markdown
---

To save recognition results to a file or write them to the memory stream, use [`Save`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/save/) method of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object.

The following file formats are supported:

Format | Description
------ | -----------
`Aspose.OCR.SaveFormat.Text` | Plain text with line breaks.
`Aspose.OCR.SaveFormat.Pdf` | Portable Document Format. The original images are placed in the background; the recognized text is placed as an invisible but searchable and selectable overlay on top of the images.
`Aspose.OCR.SaveFormat.PdfNoImg` | Portable Document Format containing only text. The original images are not saved along with the recognition results.
`Aspose.OCR.SaveFormat.Docx` | Microsoft Word document (version 2007 or later).
`Aspose.OCR.SaveFormat.Xlsx` | Microsoft Excel spreadsheet (version 2007 or later).
`Aspose.OCR.SaveFormat.Json` | JSON is a popular format widely used in software development and data exchange. The de facto standard for websites and REST APIs.
`Aspose.OCR.SaveFormat.Xml` | Extensible Markup Language (XML), a universal data exchange and storage format for most systems.
`Aspose.OCR.SaveFormat.HTML` | HTML web page.
`Aspose.OCR.SaveFormat.EPUB` | ePub, a popular e-book file format.
`Aspose.OCR.SaveFormat.RTF` | RTF, a universal format for exchanging text documents between different word processing programs.
`Aspose.OCR.SaveFormat.HOCR` | hOCR, an open standard of data representation for formatted text obtained from OCR. It includes extracted text, style, layout, and other information.
`Aspose.OCR.SaveFormat.Md` | Markdown. Can contain images.

You can optionally enable [automatic spelling corrections](/ocr/net/automatic-spelling-correction/) for recognition results, provide a [custom dictionary](/ocr/net/dictionaries/), or specify the font to be embedded into a PDF document. The latter is only applicable when saving recognition results into text-only PDF (`Aspose.OCR.SaveFormat.PdfNoImg`).

{{< tabs tabID="1" tabTotal="2" tabName1="Save to file" tabName2="Write to memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Save result
results[0].Save("result.txt", Aspose.OCR.SaveFormat.Text);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add an image to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source.png");
// Recognize image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input);
// Save result
using(MemoryStream ms = new MemoryStream())
{
	results[0].Save(ms, Aspose.OCR.SaveFormat.Text);
}
```
{{< /tab >}}
{{< /tabs >}}

## Saving recognition results as a multi-page document

You can merge several recognition results into one document using [`SaveMultipageDocument`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/savemultipagedocument/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

You can optionally enable [automatic spelling corrections](/ocr/net/automatic-spelling-correction/) for recognition results and provide a [custom dictionary](/ocr/net/dictionaries/).

{{< tabs tabID="2" tabTotal="2" tabName1="Save to file" tabName2="Write to memory" >}}
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
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.docx", Aspose.OCR.SaveFormat.Docx, results);
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
	Aspose.OCR.AsposeOcr.SaveMultipageDocument(ms, Aspose.OCR.SaveFormat.Docx, results);
}
```
{{< /tab >}}
{{< /tabs >}}
