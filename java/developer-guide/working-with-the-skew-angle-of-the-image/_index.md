---
title: Working with the Skew Angle of the Image
type: docs
weight: 20
url: /java/working-with-the-skew-angle-of-the-image/
aliases:
    - /java/calculate-skew-angle-of-the-image/
---

## Calculate Skew Angle of the Image

Aspose.OCR provides the [**CalcSkewImage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#CalcSkewImage-java.lang.String-) method that calculates the skew angle of the image. The [**CalcSkewImage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#CalcSkewImage-java.lang.String-) method takes the image path as a parameter and returns the skew angle. The following code snippet demonstrates the use of the [**CalcSkewImage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#CalcSkewImage-java.lang.String-) method to calculate the skew angle of an image.

{{< gist "aspose-com-gists" "3830491066e58e54903b3025d04e5b0c" "Examples-src-main-java-com-aspose-ocr-examples-OcrFeatures-CalculateSkewAngle-1.java" >}}

## Set Custom Angle for Skew Correction

Aspose.OCR for Java provides to option to specify custom angle for skew correction. For this, the API provides the [**RecognitionSettings.setSkew**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setSkew-double-) method. You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class to the [**RecognizePage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage-java.awt.image.BufferedImage-com.aspose.ocr.RecognitionSettings-) method of the [**AsposeOCR**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

The following code snippet demonstrates the use of the [**RecognitionSettings.setSkew**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setSkew-double-) property to set custom skew correction angle.

{{< gist "aspose-com-gists" "3830491066e58e54903b3025d04e5b0c" "Examples-src-main-java-com-aspose-ocr-examples-OcrFeatures-OCROperationWithLanguageSelection-1.java" >}}
