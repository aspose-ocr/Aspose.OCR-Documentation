---
title: Detect Areas Mode
type: docs
weight: 80
url: /net/detect-areas-mode/
---
## **Detect Areas Mode**
Aspose.OCR for .NET provides to option to specify the area recognition method. 
For this, the API provides the [**RecognitionSettings.DetectAreasMode **](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/detectareasmode) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) 
method of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the DetectAreasMode  property. 
You can disable regions detection and use DetectAreasMode.NONE, or you can choose the best region detection method according to placing text on your image. 
So in some cases, using [**RecognitionSettings.DetectAreasMode **](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/detectareasmode) you can get a better recognition result.


## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();
	// The image path
	String imagePath = dataDir + "table.png";

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// Recognize image
	RecognitionResult result = api.RecognizeImage(imagePath, new RecognitionSettings
	{
		DetectAreasMode = DetectAreasMode.PHOTO
		// DetectAreasMode.NONE - faster but can recognize only simple text
		// DetectAreasMode.DOCUMENT - best for the multicolumn text, text with small images. Slowest one.
		// DetectAreasMode.PHOTO - best for the images with small text regions, some tables, receipts, invoices
		// DetectAreasMode.COMBINE - uses the union of DOCUMENT and PHOTO modes
		// DetectAreasMode.TABLE - preferable mode for images with table structure.
	});

	// Display the recognized text
	Console.WriteLine(result.RecognitionText);			
			
{{< /highlight >}}


