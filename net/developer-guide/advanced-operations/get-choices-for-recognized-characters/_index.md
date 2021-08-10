---
title: Get the set of characters with the alternatives
type: docs
weight: 20
url: /net/get-choices-for-recognized-characters/
description: This article explains how to get image recognition characters and choices to replace them with Aspose.OCR for .NET.
---

## Recognize Text on Image with Characters Choices

Aspose.OCR for .NET provides a set of characters found by the recognition algorithm and arranged in descending order of probability. The following code shows how to get the array of symbols (char[]) with the maximum probability and alternatives using C#:


```csharp
public static void RecognizeAndGetChoices()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();

	// Recognize image           
	RecognitionResult result = api.RecognizeImage(fullPath, new RecognitionSettings
	{
		//default or custom
	});

	List<char[]> resultWithChoices = result.RecognitionCharactersList;
	// Print result
	Console.WriteLine($"Text:\n {result.RecognitionText}");
	Console.WriteLine("Choices:");
	resultWithChoices.ForEach(a => Console.WriteLine($"character: {a[0]} . Choices: {a[1]} {a[2]} {a[3]} {a[4]}"));
}
```
