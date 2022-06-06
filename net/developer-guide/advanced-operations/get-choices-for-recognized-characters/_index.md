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

<style>
p { text-align: center; padding: 10px; }
label { display: inline-block; padding: 4px 6px; border: 1px solid #333; background-color: rgba(32, 32, 32, 0.9); border-radius: 6px; font-size: 80%; font-weight: bold; color: #fff; }
label:hover, label:active, input:hover+label, input:active+label {
    background:grey;
}
</style>

<a href="https://downgit.github.io/#/home?url=https://github.com/aspose-ocr/Aspose.OCR-for-.NET/blob/master/README.md" ><label for="overlay">Download example</label></a>


