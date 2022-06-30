---
title: Get OCR Result as JSON
type: docs
weight: 70
url: /cpp/get-ocr-result-as-json/
---

## **Get OCR Result as JSON**

Aspose.OCR for C++ can return recognition results in JSON format - the most popular popular open standard format for describing nested data structures.

To get recognition results in JSON format, set the [`format`](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#aab0df293b6cdbb8289677e42747697ee) property of [`RecognitionSettings`](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings) to `export_format::json` and pass it as a parameter to the `page_from_uri` method.

## Example

{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-PerformOCROnImageFromUrl.cpp" >}}
