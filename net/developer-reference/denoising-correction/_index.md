---
title: Denoising Correction
type: docs
weight: 77
url: /net/denoising-correction/
---
## **Denoising Correction Preprocessing Filters**
Aspose.OCR for .NET provides to option to specify denoising correction operation for image before recognition. 
For this, the API provides the [**RecognitionSettings.AutoDenoising**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/autodenoising) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method 
of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the AutoDenoising property. 
Usually, preprocessing operations done automatically, but denoising is enabled. So in some cases, using [**RecognitionSettings.AutoDenoising**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/autodenoising) you can get a better recognition result.


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
             AutoDenoising = true
    });
			
			
{{< /highlight >}}


