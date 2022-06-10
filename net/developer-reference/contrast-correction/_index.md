---
title: Contrast Correction
type: docs
weight: 76
url: /net/contrast-correction/
---
## **Contrast Correction Preprocessing Filters**
Aspose.OCR for .NET provides to option to specify contrast correction operation for image before recognition. 
For this, the API provides the [**RecognitionSettings.AutoContrast**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/autocontrast) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the AutoContrast property. 
Usually, preprocessing operations done automatically, but contrast correction is enabled. So in some cases, using [**RecognitionSettings.AutoContrast**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/autocontrast) you can get a better recognition result.


## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();
	// The image path
	String imagePath = dataDir + "0001460985.Jpeg";

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// Recognize with contrast correction
	var resultWithPreprocess = api.RecognizeImage(imagePath, new RecognitionSettings
    {
             AutoContrast = true
    });
			
			
{{< /highlight >}}


