---
title: Recognize multi images
type: docs
weight: 75
url: /net/folders-and-archives/
---
## **Recognize archive**

Aspose.OCR for .NET provides the method [**RecognizeMultipleImages**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) that allows to recognize a multi images with one call. The result you will get is array of the [**RecognitionResult**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionresult) class.

The following code snippet demonstrates the use of the [**RecognizeMultipleImages**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) method.

## Sample Code 

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Archive Path
	string fullPath = dataDir + "OCR.zip";

	// Recognize images           
	RecognitionResult[] result = api.RecognizeMultipleImages(fullPath, new RecognitionSettings
	{
	   //default or custom
	});

	// Print result
	for (int i = 0; i < result.Length; i++)
	{
		 Console.WriteLine($"Image: {i}\n Result:\n {result[i].RecognitionText}");
	}
{{< /highlight >}}

## **Recognize folder**

## Sample Code 

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Folder Path
	string fullPath = dataDir + "OCR";

	// Recognize images           
	RecognitionResult[] result = api.RecognizeMultipleImages(fullPath, new RecognitionSettings
	{
	   //default or custom
	});

	// Print result
	for (int i = 0; i < result.Length; i++)
	{
		 Console.WriteLine($"Image: {i}\n Result:\n {result[i].RecognitionText}");
	}
{{< /highlight >}}
