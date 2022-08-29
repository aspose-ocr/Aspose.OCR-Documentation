---
title: Result get split lines with coordinates and with text
type: docs
weight: 65
url: /net/result-get-lines/
---

## **Result get split lines with coordinates and with text**

Aspose.OCR for .NET provides the option to get the result as split lines [**RecognitionResult.LinesResult**](https://reference.aspose.com/ocr/net/aspose.ocr.recognitionresult/linesresult). 
For this, the API provides the property[**RecognitionResult.RecognitionLinesResult**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/properties/recognitionlinesresult).

The following code snippet demonstrates the use of the [**RecognitionResult.RecognitionLinesResult**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/properties/recognitionlinesresult).

# Sample Code 

```csharp

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// Recognize image           
    RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings());

    // Get result
	  Console.WriteLine($"Text: {result.RecognitionText}");
            Console.WriteLine($"skew: {result.Skew}");
            Console.WriteLine("Areas:");
            result.RecognitionAreasText.ForEach(a => Console.WriteLine($"{a}"));

            Console.WriteLine("Lines:");
            result.RecognitionLinesResult.ForEach(a => Console.WriteLine($"{a.TextInLine}"));
			result.RecognitionLinesResult.ForEach(a => Console.WriteLine($"X: {a.Line.X} Y: {a.Line.Y} Width: {a.Line.Width} Height: {a.Line.Height}"));

            Console.WriteLine("Choices:");
            result.RecognitionCharactersList.ForEach(a => Console.WriteLine($"{a[0]} {a[1]} {a[2]} {a[3]} {a[4]}"));

            Console.WriteLine("Warnings:");
            result.Warnings.ForEach(w => Console.WriteLine($"{w}"));
            result.RecognitionAreasRectangles.ForEach(w => Console.WriteLine($"{w.X} {w.Y} {w.Width} {w.Height}"));

            Console.WriteLine($"JSON: {result.GetJson()}");
            Console.WriteLine("\n----------------------------------------");
	}
	
	Console.WriteLine(api.CorrectSpelling("recogniition"));
```


