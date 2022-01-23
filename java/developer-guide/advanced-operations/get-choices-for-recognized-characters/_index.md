---
title: Get the set of characters with the alternatives
type: docs
weight: 20
url: /java/get-choices-for-recognized-characters/
description: This article explains how to get image recognition characters and choices to replace them with Aspose.OCR for Java.
---

## Recognize Text on Image with Characters Choices

Aspose.OCR for Java provides a set of characters found by the recognition algorithm and arranged in descending order of probability. 
The following code shows how to get the array of symbols (char[]) with the maximum probability and alternatives using Java:


```csharp
public static void RecognizeAndGetChoices()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOCR api = new AsposeOCR();

	// Recognize image           
	RecognitionResult result = api.RecognizePage(fullPath, new RecognitionSettings());//settings default or custom


	// Print result
		System.out.println("Result: " + result.recognitionText);
		 for(int j = 0; j < result.recognitionCharactersList.size(); j++) {
		  System.out.print(result.recognitionCharactersList.get(j)[0] + " ");
		  System.out.print(result.recognitionCharactersList.get(j)[1] + " ");
		  System.out.print(result.recognitionCharactersList.get(j)[2] + " ");
		  System.out.print(result.recognitionCharactersList.get(j)[3] + " ");
		  System.out.println(result.recognitionCharactersList.get(j)[4] + " "); 
		 }
		 
}
```
