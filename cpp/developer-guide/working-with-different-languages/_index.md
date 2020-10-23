---
title: Working with different languages
type: docs
weight: 30
url: /cpp/working-with-different-languages/
---

## Perform OCR Operation without specifying language

Aspose.OCR for C++ can recognize characters other than Latin. For the complete list of characters, please visit the following page.

[Supported Characters](/ocr/cpp/supported-characters/)

There is no difference in performing OCR operation on images containing text in languages other than English. The following code snippet demonstrates performing OCR operation on an image containing Spanish text.

{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-WorkingWithDifferentLanguages.cpp" >}}

## Select Language for OCR Operation

Aspose.OCR for C++ provides the option to specify the language to increase the efficiency of the OCR operation. For this, the API provides the [**RecognitionSettings.language_alphabet**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#ae656be81807ebf1f6f1fa17694d458b9) property. The [**RecognitionSettings.language_alphabet**](https://apireference.aspose.com/ocr/cpp/struct/recognition_settings#ae656be81807ebf1f6f1fa17694d458b9) property accepts the language enum as value. The language enum has the following members.

|Member|Language|
| :- | :- |
|none|Multi-language support|
|en|English (en)|
|de|German (de)|
|pt|Portuguese (pt)|
|es|Spanish (es)|
|fr|French (fr)|
|it|Italian (it)|

The following code snippet demonstrates selecting language for OCR operation.

{{< gist "aspose-com-gists" "0a96b16b37da1f556e7081063782ec02" "Aspose.OCR-for-C-main-OCROperationWithLanguageSelection.cpp" >}}
