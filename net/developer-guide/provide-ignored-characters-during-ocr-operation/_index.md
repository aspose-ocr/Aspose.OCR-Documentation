---
title: Provide ignored characters during OCR operation
type: docs
weight: 60
url: /net/provide-ignored-characters-during-ocr-operation/
---

## **Provide ignored characters during OCR operation**
In case you know the characters that aren't present in the image, you can pass those characters as a value for property 
[**RecognitionSettings.IgnoredCharacters **](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/ignoredcharacters). Doing this will ensure that the provided characters aren't matched in the OCR process. The following code snippet demonstrates setting the ignored characters for the OCR process.

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
		IgnoredCharacters  = "ab1"
	});
			
	// Display the recognized text
	Console.WriteLine(result.RecognitionText);
{{< /highlight >}}

