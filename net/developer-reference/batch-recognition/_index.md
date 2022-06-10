---
title: Recognize multi images
type: docs
weight: 70
url: /net/batch-recognition/
---

## **Recognize archive**

Aspose.OCR for .NET provides the method [**RecognizeMultipleImages**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) that allows to recognize a multi images with one call. The result you will get is array of the [**RecognitionResult**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionresult) class.

The following code snippet demonstrates the use of the [**RecognizeMultipleImages**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) method.

# Sample Code 

```csharp
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
```

## **Recognize folder**

# Sample Code 

```csharp

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
```

## **Recognize list**

# Sample Code 

```csharp

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	{
	string dataDir = RunExamples.GetDataDir_OCR();

		// Recognize images           
		RecognitionResult[] result = api.RecognizeMultipleImages(
                    new List<string>
                    {
                        "dataDir/firstImag.png",
                        "dataDir/secondImg.jpg"
                    },
                    new RecognitionSettings
                    {
					    // set as you need
                        DetectAreas = true,
                        LinesFiltration = false,
                        ThreadsCount = 1
                    });

		for (int i = 0; i < result.Length; i++)
		{
			PrintRecognitionResult(result[i]);
		}
	}

	// Print result
	static void PrintRecognitionResult(RecognitionResult result)
    {
            Console.WriteLine($"Text: {result.RecognitionText}");
            Console.WriteLine($"skew: {result.Skew}");
            Console.WriteLine("Paragraphes:");
            result.RecognitionAreasRectangles.ForEach(w => Console.WriteLine($"{w.X} {w.Y} {w.Width} {w.Height}"));
            Console.WriteLine("Text in Paragraphes:");
            result.RecognitionAreasText.ForEach(a => Console.WriteLine($"{a}"));

            Console.WriteLine("Lines:");
            result.RecognitionLinesResult.ForEach(a => Console.WriteLine($"X: {a.Line.X} Y: {a.Line.Y} Width: {a.Line.Width} Height: {a.Line.Height}\n{a.TextInLine}"));

          //  Console.WriteLine("Choices:");
          //  result.RecognitionCharactersList.ForEach(a => Console.WriteLine($"{a[0]} {a[1]} {a[2]} {a[3]} {a[4]}"));

            Console.WriteLine($"JSON: {result.GetJson()}");


            Console.WriteLine("Warnings:");
            result.Warnings.ForEach(w => Console.WriteLine($"{w}"));

            Console.WriteLine("\n----------------------------------------");
    }
```
