---
weight: 50
date: "2022-12-09"
author: "Vladimir Lapin"
type: docs
url: /cpp/areas-detection/
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

You can manually override the default document areas detection method if you are unhappy with the results or get unwanted artifacts. Document structure analysis algorithm is specified in an optional `detect_areas_mode` parameter of [recognition settings](https://reference.aspose.com/ocr/cpp/struct/recognition_settings/).

```cpp
std::string image_path = "source.png";
const size_t len = 4096;
wchar_t buffer[len] = { 0 };
RecognitionSettings settings;
settings.detect_areas_mode = detect_areas_mode_enum::CURVED_TEXT;
size_t res_len = aspose::ocr::page_settings(image_path.c_str(), buffer, len, settings);
std::wcout << buffer;
```

Aspose.OCR for C++ supports the following document structure analysis methods provided in `detect_areas_mode_enum` enumeration:

Name              | Value | Description | Use cases
----------------- | :---: | ----------- | ---------
`detect_areas_mode_enum::NONE` | 0 | Do not analyze document structure. Never disable automatic document areas detection when working with multi-paragraph and multi-column documents, tables, or photos. This can significantly reduce recognition accuracy. | Simple images containing a few lines of text without illustrations or formatting.<br />Applications requiring maximum recognition speed<br />Web applications
`detect_areas_mode_enum::DOCUMENT` | 1 | Detect large blocks of text, such as paragraphs and columns. Optimal for multi-column documents with illustrations.<br />See [**detect_areas_mode_enum::DOCUMENT**](/ocr/cpp/areas-detection/document/) for additional details. | Contracts<br />Books<br />Articles<br />Newspapers<br />High-quality scans
`detect_areas_mode_enum::PHOTO` | 2 | Finds small text blocks inside complex images.<br />See [**detect_areas_mode_enum::PHOTO**](/ocr/cpp/areas-detection/photo/) for additional details. | Driver’s licenses<br />Social security cards<br />Government and work IDs<br />Visas<br />Photos<br />Screenshots<br />Advertisements
`detect_areas_mode_enum::COMBINE` | 3 | The combination of _detect_areas_mode_enum::DOCUMENT_ and _detect_areas_mode_enum::PHOTO_.<br />See [**detect_areas_mode_enum::COMBINE**](/ocr/cpp/areas-detection/combine/) for additional details. | Posters<br />Billboards<br />Datasheets<br />Random photos<br />Batch recognition
`detect_areas_mode_enum::TABLE` | 4 | Detects cells in tabular structures.<br />See [**detect_areas_mode_enum::TABLE**](/ocr/cpp/areas-detection/table/) for additional details. | Tables<br />Invoices
`detect_areas_mode_enum::CURVED_TEXT` | 5 | Auto-straightens curved lines and finds text blocks inside the resulting image.<br />See [**detect_areas_mode_enum::CURVED_TEXT**](/ocr/cpp/areas-detection/curved_text/) for additional details. | Photos of books, magazine articles, and other curved pages.
