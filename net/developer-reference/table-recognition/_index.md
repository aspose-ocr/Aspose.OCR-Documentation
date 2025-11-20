---
weight: 68
date: "2025-11-18"
author: "Anna Pylaieva"
type: docs
url: /net/table-recognition/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
aliases:
- /net/recognition/image/
- /net/recognition/pdf/
- /net/recognition/tiff/
- /net/recognition/djvu/
- /net/recognition/url/
- /net/batch-recognition/
- /net/recognition/pixel/
- /net/recognition/base64/
- /net/recognition/table/
feedback: OCRNET
title: Table recognition
description: Extracting and recognizing table cells from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- table
- extract
- OCR
- recognize
---

Aspose.OCR for .NET now provides a dedicated API for detecting table layout and recognizing table data in images, scanned documents, screenshots, or photos.
To extract formula text, simply call the universal [`Aspose.OCR.AsposeOcr.Recognize`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognize/) method with [`DetectAreasMode.TABLE`](https://reference.aspose.com/ocr/net/aspose.ocr/detectareasmode/) settings.

This method accepts an `OcrInput` object and optional recognition settings.

Recognition results are returned as a list of `Aspose.OCR.RecognitionResult` objects. Each result contains extracted table data, detected regions, and allows exporting to various formats.
Additionally, you can retrieve the table's row and column structure using the [`GetTebleData()`](https://reference.aspose.com/ocr/net/aspose.ocr/ocroutput/gettabledata/) method.

## DetectAreasMode.TABLE

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("source1.png");
input.Add("source2.jpg");
// Configure recognition settings for formulas
Aspose.OCR.RecognitionSettings settings = new Aspose.OCR.RecognitionSettings();
settings.DetectAreasMode = Aspose.OCR.DetectAreasMode.TABLE;
// Recognize formulas on the image
Aspose.OCR.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
OCRTable table = results.GetTableData();
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
