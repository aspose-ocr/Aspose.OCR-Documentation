---
title: Working with different languages
type: docs
weight: 20
url: /net/working-with-different-languages/
---

## Perform OCR Operation without specifying language

Aspose.OCR for .NET can recognize characters other than Latin. For the complete list of characters, please visit the following page.

[Supported Characters](/ocr/net/supported-characters/)

There is no difference in performing OCR operation on images containing text in languages other than English. The following code snippet demonstrates performing OCR operation on an image containing Spanish text.

{{< gist "aspose-com-gists" "dad6b4a35169ed7893fd376e819d7626" "Examples-CSharp-PerformingandManagingOCR-WorkingWithDifferentLanguages-1.cs" >}}

## Select Language for OCR Operation

Aspose.OCR for .NET provides the option to specify the language to increase the efficiency of the OCR operation. For this, the API provides the [**RecognitionSettings.Language**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/language) property. The [**RecognitionSettings.Language**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/language) property accepts the [**Language**](https://apireference.aspose.com/ocr/net/aspose.ocr/language) enumeration as value. You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class. The [**Language**](https://apireference.aspose.com/ocr/net/aspose.ocr/language) enum has the following members.

|Member|Language|
| :- | :- |
|**None**|Multi-language support|
|**En**|English (en)|
|**De**|German (de)|
|**Pt**|Portuguese (pt)|
|**Es**|Spanish (es)|
|**Fr**|French (fr)|
|**It**|Italian (it)|

The following code snippet demonstrates selecting language for OCR operation.

{{< gist "aspose-com-gists" "dad6b4a35169ed7893fd376e819d7626" "Examples-CSharp-PerformingandManagingOCR-OCROperationWithLanguageSelection-1.cs" >}}
