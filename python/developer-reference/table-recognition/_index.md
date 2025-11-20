---
weight: 58
date: "2025-11-27"
author: "Anna Pylaieva"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/table-recognition/
aliases:
- /python-net/recognition/read-text-in-wild/
feedback: OCRPYNET
title: Table recognition
description: Extracting and recognizing table cells from images, web links, scanned PDFs, DjVu files, folders, archives and other content.
keywords:
- table
- extract
- OCR
- recognize
---

Aspose.OCR for Python via .NET now provides a dedicated API for detecting table layout and recognizing table data in images, scanned documents, screenshots, or photos.
To extract table text, simply call the universal [`aspose.ocr.AsposeOcr.recognize`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/#methods) method with [`DetectAreasMode.TABLE`](https://reference.aspose.com/ocr/python-net/aspose.ocr/detectareasmode/) settings.

This method accepts an `OcrInput` object and optional recognition settings.

Recognition results are returned as a list of `aspose.ocr.RecognitionResult` objects. Each result contains extracted table data, detected regions, and allows exporting to various formats.
Additionally, you can retrieve the table's row and column structure using the [`get_table_data()`](https://reference.aspose.com/ocr/python-net/aspose.ocr/ocroutput/) method.

## Example

The following code example shows how to extract text from table and get rows and columns structure:

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("source1.png")

# Set areas detection mode
recognitionSettings = RecognitionSettings()
recognitionSettings.detect_areas_mode = DetectAreasMode.TABLE
# Recognize the image
results = api.recognize(input, recognitionSettings)

# Print recognition result
for result in results:
    print(result.recognition_text)

# Print table rows cloumns
 table =  results.get_table_data()
        for page in table.pages:
            print("page:" + str(page.page_index))
            for row in page.rows:
                print("row:" + str(row.row_index))
                for cell in row.cells:
                    print("cell:" + str(cell.column_index)+": "+cell.text)
```
