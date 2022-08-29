---
title: Custom Image Correction Using Threshold Setting
type: docs
weight: 75
url: /net/custom-image-correction-with-threshold-setting/
---
## **Custom Image Correction Using Threshold Setting**
Aspose.OCR for .NET provides to option to specify custom threshold value for image quality correction. For this, the API provides the [**RecognitionSettings.ThresholdValue**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/tresholdvalue) property. You can pass the instance of the [**RecognitionSettings**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method of the [**AsposeOcr**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the [**ThresholdValue**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/thresholdvalue) property provides custom image quality correction. 
Usually, threshold value calculated automatically, but in some cases, using [**ThresholdValue**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/thresholdvalue) property can get better recognition result. You can customize it from 1 to 255 value. If you set  the [**ThresholdValue**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/thresholdvalue) as 0 (zero), this value will be calculated automatically.


## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// Recognize image
	RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings
	{
		ThresholdValue = 230
	});
			
	// Display the recognized text
	Console.WriteLine(result.RecognitionText);
{{< /highlight >}}


