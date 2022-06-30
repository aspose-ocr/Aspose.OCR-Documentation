---
title: Get OCR Result as file
type: docs
weight: 75
url: /cpp/get-ocr-result-as-file/
---
## **Get OCR Result as file**

Aspose.OCR for C++ provides the method [**page_save()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga248e71b77ac6dbaf0c80630b2181cf29) to get the result in Document format.

The following code snippet demonstrates the use of the [**page_save()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga248e71b77ac6dbaf0c80630b2181cf29) method 
to save the recognition result in file.

## Sample Code

Visit https://github.com/aspose-ocr/Aspose.OCR-for-C for the full project and sample data files.

```cpp
directory dir(".");
const string current_dir = dir.full_name();
const string image = current_dir + "p.png";

const size_t len = 6000;
wchar_t buffer[len] = { 0 };

/** To select the desired file format, uncomment the corresponding line  */
RecognitionSettings settings;
//settings.all_image = false;
//settings.format = export_format::json;
settings.save_format = file_format::docx;

aspose::ocr::page_save(image.c_str(), "cpp_res.docx", settings);
```

## Select file format for result

Aspose.OCR.Cpp provides the option to specify the Document format for result saving. For this, the API provides the [**save_format**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#ac011403d84ee28fc62fe1d9bec824c2d) 
enumeration. The [**save_format**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#ac011403d84ee28fc62fe1d9bec824c2d) enum has the following members.

Member | Description
------ | -----------
**file_format::txt** | Save recognition results as a plain text file.
**file_format::docx** | Save recognition results as a Microsoft Word 2007+ file (DOCX).
**file_format::pdf** | Save recognition results a PDF document.
**file_format::xlsx** | Save recognition results a Microsoft Excel 2007+ workbook (XLSX).
**file_format::json** | Save recognition results as a file in JSON format.
