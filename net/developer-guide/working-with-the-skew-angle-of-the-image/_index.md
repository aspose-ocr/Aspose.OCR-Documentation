---
title: Working with the Skew Angle of the Image
type: docs
weight: 30
url: /net/working-with-the-skew-angle-of-the-image/
aliases:
    - /net/calculate-skew-angle-of-the-image/
---

## Calculate Skew Angle of the Image

Aspose.OCR provides the [**CalculateSkew**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/calculateskew/methods/1) method that calculates the skew angle of the image. The [**CalculateSkew**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/calculateskew/methods/1) method takes the image path as a parameter and returns the skew angle. The following code snippet demonstrates the use of the [[**CalculateSkew**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/calculateskew/methods/1) method to calculate the skew angle of an image.

{{< gist "aspose-com-gists" "dad6b4a35169ed7893fd376e819d7626" "Examples-CSharp-PerformingandManagingOCR-CalculateSkewAngle-1.cs" >}}

## Calculate Skew Angle of the Image using stream

You may also calculate the skew angle using streams. For this, the API provides the overloaded method [**CalculateSkew**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/calculateskew) that takes memory stream as a parameter. The following code snippet demonstrates the use of the [**CalculateSkew**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/calculateskew) method to calculate the skew angle of an image with a memory stream.

{{< gist "aspose-com-gists" "dad6b4a35169ed7893fd376e819d7626" "Examples-CSharp-PerformingandManagingOCR-CalculateSkewAngleFromStream-1.cs" >}}

## Set Custom Angle for Skew Correction

Aspose.OCR for .NWT provides to option to specify custom angle for skew correction. For this, the API provides the [**RecognitionSettings.Skew**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/skew) method. You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the [**RecognitionSettings.Skew**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/skew) property to set custom skew correction angle.

{{< gist "aspose-com-gists" "dad6b4a35169ed7893fd376e819d7626" "Examples-CSharp-PerformingandManagingOCR-OCROperationWithLanguageSelection-1.cs" >}}
