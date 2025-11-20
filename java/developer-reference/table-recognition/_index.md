---
weight: 58
date: "2025-11-19"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /java/table-recognition/
aliases:
- /ocr/java/recognition/image/
- /ocr/java/recognition/pdf/
- /ocr/java/recognition/tiff/
- /ocr/java/recognition/url/
- /ocr/java/batch-recognition/
- /java/recognition/read-text-in-wild/
feedback: OCRJAVA
title: Table recognition
description: Extracting and recognizing table cells from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- table
- extract
- OCR
- recognize
---

Aspose.OCR for Java now provides a dedicated API for detecting table layout and recognizing table data in images, scanned documents, screenshots, or photos.
To extract table text, simply call the universal [`com.aspose.ocr.AsposeOCR.Recognize`](https://reference.aspose.com/ocr/java/com.aspose.ocr/asposeocr/#Recognize-com.aspose.ocr.OcrInput-com.aspose.ocr.RecognitionSettings) method with [`DetectAreasMode.TABLE`](https://reference.aspose.com/ocr/java/com.aspose.ocr.models/detectareasmode/) settings.

This method accepts an `OcrInput` object and optional recognition settings.

Recognition results are returned as a list of `com.aspose.ocr.AsposeOCR.RecognitionResult` objects. Each result contains extracted table data, detected regions, and allows exporting to various formats.
Additionally, you can retrieve the table's row and column structure using the [`GetTableData()`](https://reference.aspose.com/ocr/java/com.aspose.ocr/ocroutput/#getTableData) method.

## DetectAreasMode.TABLE and GetTableData

The following code example shows how to extract text from table and get rows and columns structure:

```java
com.aspose.ocr.AsposeOCR recognitionEngine = new com.aspose.ocr.AsposeOCR();
// Add images to OcrInput object
com.aspose.ocr.OcrInput input = new com.aspose.ocr.OcrInput(InputType.SingleImage);
input.add("source1.png");
input.add("source2.jpg");
// Configure recognition settings for tables
com.aspose.ocr.RecognitionSettings settings = new com.aspose.ocr.RecognitionSettings();
settings.setDetectAreasMode(DetectAreasMode.TABLE);
// Recognize tables on the image
com.aspose.ocr.OcrOutput results = recognitionEngine.Recognize(input, recognitionSettings);
com.aspose.ocr.models.OCRTable table = results.GetTableData();

results.forEach((result) -> {
	System.out.println(result.recognition_text);
});


// Print recognized table data in rows and cols
for(OCRTablePage page : table.getPages()) {
    System.out.println("page index: "+page.getPageIndex());
    for(OCRTableRow row : page.getRows()) {
        System.out.println("row index: "+row.getRowIndex());
        for(OCRTableCell cell : row.getCells()) {
            System.out.print("cell index: "+cell.getColumnIndex()+": ");
            System.out.println(cell.getText());
        }
    }
}
```

