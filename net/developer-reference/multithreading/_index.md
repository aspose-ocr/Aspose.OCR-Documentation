---
title: Multithreading support in recognition
type: docs
weight: 75
url: /net/multithreading-support-in-recognition/
---
## **Multithreading support in recognition**
Aspose.OCR for .NET provides to option to specify threads count value to increase performance. 
For this, the API provides the [**RecognitionSettings.ThreadsCount**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/threadscount) property. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings) class to the [**RecognizeImage**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizeimage/index) method of the [**AsposeOcr**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr) class.

The following code snippet demonstrates the use of the [**ThreadsCount**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/threadscount) property provides custom number of threads. 
ThreadsCount by default equals customer processors number, but using [**ThreadsCount**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/threadscount) property can get better perfomance. You can customize it from 0. If you set  the [**ThreadsCount**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/thresholdvalue) as 0 (zero), this value will be calculated automatically and equal to the number of cores of your processor..


## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	{
		// The path to the documents directory.
		string dataDir = RunExamples.GetDataDir_OCR();

		// Initialize an instance of AsposeOcr
		AsposeOcr api = new AsposeOcr();

		// Recognize image in main thread
		 RecognitionResult result = api.RecognizeImage("imgs/full.png", new RecognitionSettings { ThreadsCount = 1 });
				ConsoleLogRecognitionResult(result);

		// Recognize image using 4 threads
		result = api.RecognizeImage("imgs/full.png", new RecognitionSettings { ThreadsCount = 4 });
				ConsoleLogRecognitionResult(result);
			
	}
	
	// Display the recognized text
    static void ConsoleLogRecognitionResult(RecognitionResult result)
	{
		Console.WriteLine($"Text: {result.RecognitionText}");
		Console.WriteLine($"skew: {result.Skew}");
		Console.WriteLine("Areas coordinates:");
		result.RecognitionAreasRectangles.ForEach(a => Console.WriteLine($"x: {a.X} y: {a.Y} width: {a.Width} height: {a.Height}"));

		Console.WriteLine("Areas text:");
		result.RecognitionAreasText.ForEach(a => Console.WriteLine($"{a}"));

		Console.WriteLine("Lines:");
		result.RecognitionLinesResult.ForEach(a => Console.WriteLine($"x: {a.Line.X} y: {a.Line.Y} width: {a.Line.Width} height: {a.Line.Height}\n{a.TextInLine}"));

		Console.WriteLine("Choices:");
		//   result.RecognitionCharactersList.ForEach(a => Console.WriteLine($"{a[0]} {a[1]} {a[2]} {a[3]} {a[4]}"));

		Console.WriteLine("Warnings:");
		result.Warnings.ForEach(w => Console.WriteLine($"{w}"));

		Console.WriteLine($"JSON: {result.GetJson()}");
		Console.WriteLine("\n----------------------------------------");
	}
{{< /highlight >}}


