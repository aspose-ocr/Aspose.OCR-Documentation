---
weight: 50
date: "2022-07-19"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /cpp/areas-detection/
feedback: OCRCPP
aliases:
- /cpp/perform-ocr-without-automatic-text-area-detection/
- /cpp/perform-ocr-with-mode-for-text-area-detectionn/
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

You can manually override the default document areas detection function if you are unhappy with the results or get unwanted artifacts. Document structure analysis algorithm is specified in an optional `detect_areas_mode` parameter of [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/).

```cpp
// Provide the image
string file = "source.png";
AsposeOCRInput source;
source.url = file.c_str();
std::vector<AsposeOCRInput> content = { source };
// Fine-tune recognition
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::CURVED_TEXT;
// Extract text from the image
auto result = asposeocr_recognize(content.data(), content.size(), settings);
// Output the recognized text
wchar_t* buffer = asposeocr_serialize_result(result, buffer_size, export_format::text);
std::wcout << std::wstring(buffer) << std::endl;
// Release the resources
asposeocr_free_result(result);
```

Aspose.OCR for C++ supports the following document structure analysis functions provided in `detect_areas_mode_enum` enumeration:

Name              | Value | Description | Use cases
----------------- | :---: | ----------- | ---------
`detect_areas_mode_enum::NONE` | 0 | Do not analyze document structure. Never disable automatic document areas detection when working with multi-paragraph and multi-column documents, tables, or photos. This can significantly reduce recognition accuracy. | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`detect_areas_mode_enum::DOCUMENT` | 1 | Detect large blocks of text, such as paragraphs and columns. Optimal for multi-column documents with illustrations.<br />See [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers<br />High-quality scans
`detect_areas_mode_enum::PHOTO` | 2 | Finds small text blocks inside complex images.<br />See [**detect_areas_mode_enum::PHOTO**](/ocr/cpp/areas-detection/photo/) for additional details. | Driver’s licenses<br />Social security cards<br />Government and work IDs<br />Visas<br />Photos<br />Screenshots<br />Advertisements
`detect_areas_mode_enum::MIXED_TEXT` | 3 | The combination of _detect_areas_mode_enum::DOCUMENT_ and _detect_areas_mode_enum::PHOTO_.<br />See [**detect_areas_mode_enum::MIXED_TEXT**](/ocr/cpp/areas-detection/mixed_text/) for additional details. | Posters<br />Billboards<br />Datasheets<br />Random photos<br />Batch recognition
`detect_areas_mode_enum::TABLE` | 4 | Detects cells in tabular structures.<br />See [**detect_areas_mode_enum::TABLE**](/ocr/cpp/areas-detection/table/) for additional details. | Tables<br />Invoices
`detect_areas_mode_enum::CURVED_TEXT` | 5 | Auto-straightens curved lines and finds text blocks inside the resulting image.<br />See [**detect_areas_mode_enum::CURVED_TEXT**](/ocr/cpp/areas-detection/curved_text/) for additional details. | Photos of books, magazine articles, and other curved pages.
`detect_areas_mode_enum::UNIVERSAL` | 6 | Optimal choice for general image processing. However, specialized algorithms can provide faster or more accurate results for their intended use cases.<br />See [**detect_areas_mode_enum::UNIVERSAL**](/ocr/cpp/areas-detection/universal/) for additional details. | On average, this algorithm achieves good results with most image types.

## Performance impact

Pipeline | Time
-------- | ----
`detect_areas_mode_enum::PHOTO` | 2.9 seconds
`detect_areas_mode_enum::PHOTO`<br />[Recognition](/ocr/cpp/recognition/) | 4.7 seconds
`detect_areas_mode_enum::CURVED_TEXT`<br />[Recognition](/ocr/cpp/recognition/) | 8.5 seconds
