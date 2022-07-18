---
title: Perform OCR on selected areas of an image
type: docs
weight: 50
url: /net/perform-ocr-on-selected-areas-of-an-image/
---

## **Perform OCR on selected areas of an image**
Aspose.OCR for .NET provides the option to specify the areas for recognizing text in pixels. For this, the API provides the overloaded version of the [RecognizePage](https://reference.aspose.com/ocr/net/aspose.ocr.asposeocr/recognizeimage/methods/5) method that takes the image path and the RecognitionSettings object with array of [Rectangle](https://docs.microsoft.com/en-gb/dotnet/api/system.drawing.rectangle?view=netcore-3.1) as parameters. The following code snippet demonstrates recognizing text in specified rectangles.


## **Perform OCR on a specific rectangle**
The following code snippet demonstrates how to perform OCR operation on a specific rectangle area of the image.

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// Recognize image
	RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings
		RecognitionAreas = new List<Rectangle>()
		{
			new Rectangle(1,3,400,70),
			new Rectangle(1,72,400,70)
		});
			
	// Display the recognized text
	Console.WriteLine(result.RecognitionText);
{{< /highlight >}}
