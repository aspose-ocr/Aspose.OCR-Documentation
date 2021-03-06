---
title: Working with different languages
type: docs
weight: 30
url: /java/working-with-different-languages/
---

## Perform OCR Operation without specifying language

Aspose.OCR for Java can recognize characters other than Latin. For the complete list of characters, please visit the following page.

[Supported Characters](/ocr/java/supported-characters/)

There is no difference in performing OCR operation on images containing text in languages other than English. The following code snippet demonstrates performing OCR operation on an image containing Spanish text.

{{< gist "aspose-com-gists" "3830491066e58e54903b3025d04e5b0c" "Aspose.OCR-for-C-main-WorkingWithDifferentLanguages.cpp" >}}

## Select Language for OCR Operation

Aspose.OCR for Java provides the option to specify the language to increase the efficiency of the OCR operation. For this, the API provides the [**RecognitionSettings.setLanguage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setLanguage-com.aspose.ocr.RecognitionSettingsLanguage-) method. The [**RecognitionSettings.setLanguage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setLanguage-com.aspose.ocr.RecognitionSettingsLanguage-) method accepts the [**RecognitionSettings.Language**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage) enum as value. You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class to the [**RecognizePage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage-java.awt.image.BufferedImage-com.aspose.ocr.RecognitionSettings-) method of the [**AsposeOCR**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. The [**RecognitionSettings.Language**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage) enum has the following members.

|Member|Language|
| :- | :- |
|[**none**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#none)|Multi-language support|
|[**en**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#en)|English (en)|
|[**de**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#de)|German (de)|
|[**pt**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#pt)|Portuguese (pt)|
|[**es**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#es)|Spanish (es)|
|[**fr**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#fr)|French (fr)|
|[**it**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettingsLanguage#it)|Italian (it)|

The following code snippet demonstrates selecting language for OCR operation.

{{< gist "aspose-com-gists" "3830491066e58e54903b3025d04e5b0c" "Examples-src-main-java-com-aspose-ocr-examples-OcrFeatures-OCROperationWithLanguageSelection-1.java" >}}
