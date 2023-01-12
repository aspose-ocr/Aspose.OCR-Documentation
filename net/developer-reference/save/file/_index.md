---
weight: 10
date: "2023-01-12"
author: "Vladimir Lapin"
type: docs
url: /net/save-file/
aliases:
- /net/save-ocr-result-as-multipage-document/
- /net/get-ocr-result-as-file/
- /net/get-ocr-result-as-stream/
title: Saving recognition results as a file
description: Saving Aspose.OCR for .NET recognition results as PDF, text, Word, or Excel documents, as well as XML and JSON files.
keywords:
- save
- result
- file
- PDF
- Office
- Word
- Excel
- document
- spreadsheet,
- JSON,
- XML,
- text
---

To save recognition results to a file or write them to the memory stream, use [`Save`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/save/) method of [`Aspose.OCR.RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object.

The following file formats are supported:

Format | Description
------ | -----------
`Aspose.OCR.SaveFormat.Text` | Plain text with line breaks.
`Aspose.OCR.SaveFormat.Pdf` | Portable Document Format.
`Aspose.OCR.SaveFormat.Docx` | Microsoft Word document (version 2007 or later).
`Aspose.OCR.SaveFormat.Xlsx` | Microsoft Excel spreadsheet (version 2007 or later).
`Aspose.OCR.SaveFormat.Json` | JSON is a popular format widely used in software development and data exchange. The de facto standard for websites and REST APIs.
`Aspose.OCR.SaveFormat.Xml` | Extensible Markup Language (XML), a universal data exchange and storage format for most systems.
`Aspose.OCR.SaveFormat.HTML` | HTML web page.
`Aspose.OCR.SaveFormat.EPUB` | ePub, a popular e-book file format.
`Aspose.OCR.SaveFormat.RTF` | RTF, a universal format for exchanging text documents between different word processing programs.

You can optionally enable [automatic spelling corrections](/ocr/net/automatic-spelling-correction/) for recognition results and provide a [custom dictionary](/ocr/net/dictionaries/).

{{< tabs tabID="1" tabTotal="2" tabName1="Save to file" tabName2="Write to memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
result.Save("result.pdf", Aspose.OCR.SaveFormat.Pdf, true, Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng, "user-dictionary.txt");
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeImage("source.png", recognitionSettings);
using(MemoryStream ms = new MemoryStream())
{
	result.Save(ms, Aspose.OCR.SaveFormat.Pdf, true, Aspose.OCR.SpellChecker.SpellCheckLanguage.Eng, "user-dictionary.txt");
}
```
{{< /tab >}}
{{< /tabs >}}

## Saving recognition results as a multi-page document

You can merge several recognition results into one document using [`SaveMultipageDocument`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/savemultipagedocument/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class. This can be useful for recognizing books, contracts, articles, and other printouts consisting of multiple pages, as well as for batch recognition.

{{< tabs tabID="2" tabTotal="2" tabName1="Save to file" tabName2="Write to memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
List<Aspose.OCR.RecognitionResult> results = new List<Aspose.OCR.RecognitionResult>();
results.Add(recognitionEngine.RecognizeImage("page-1.png", recognitionSettings));
results.Add(recognitionEngine.RecognizeImage("page-2.png", recognitionSettings));
Aspose.OCR.AsposeOcr.SaveMultipageDocument("result.pdf", Aspose.OCR.SaveFormat.Pdf, results);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.RecognitionSettings recognitionSettings = new Aspose.OCR.RecognitionSettings();
List<Aspose.OCR.RecognitionResult> results = new List<Aspose.OCR.RecognitionResult>();
results.Add(recognitionEngine.RecognizeImage("page-1.png", recognitionSettings));
results.Add(recognitionEngine.RecognizeImage("page-2.png", recognitionSettings));
using(MemoryStream ms = new MemoryStream())
{
	Aspose.OCR.AsposeOcr.SaveMultipageDocument(ms, Aspose.OCR.SaveFormat.Pdf, results);
}
```
{{< /tab >}}
{{< /tabs >}}
