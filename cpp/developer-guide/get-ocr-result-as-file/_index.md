---
title: Get OCR Result as file
type: docs
weight: 75
url: /cpp/get-ocr-result-as-file/
---
## **Get OCR Result as file**

Aspose.OCR.Cpp provides the method [**page_save()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga248e71b77ac6dbaf0c80630b2181cf29) to get the result in Document format.

The following code snippet demonstrates the use of the [**page_save()**](https://apireference.aspose.com/ocr/cpp/groupAspose#ga248e71b77ac6dbaf0c80630b2181cf29) method 
to save the recognition result in file.

## Sample Code

```cpp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-C
	directory dir(".");
    const string current_dir = dir.full_name();
    const string image = current_dir + "p.png";

    const size_t len = 6000;
    wchar_t buffer[len] = { 0 };

    RecognitionSettings settings;
    //settings.save_format = file_format::docx;
	//settings.all_image = false;
    //settings.format = export_format::json;
    settings.save_format = file_format::docx;
	
    aspose::ocr::page_save(image.c_str(), "cpp_res.docx", settings);
```

## Select file format for result
Aspose.OCR.Cpp provides the option to specify the Document format for result saving. For this, the API provides the [**save_format**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#ac011403d84ee28fc62fe1d9bec824c2d) 
enumeration. The [**save_format**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#ac011403d84ee28fc62fe1d9bec824c2d) enum has the following members.

|Member|Description|
| :- | :- |
|**file_format::txt**|Saves the document in the plain text format.|
|**file_format::docx**|Saves the document as an Office Open XML WordprocessingML Document (macro-free).|
|**file_format::pdf** |Saves the document as an PDF (Adobe Portable Document) format.|
|**file_format::xlsx** |Saves the result as an Excel ( 2007 and later) workbook Document.|

