---
title: Result correction with spell-checking
type: docs
weight: 75
url: /net/result-correction-with-spell-checking/
---
## **Result correction with spell-checking**
Aspose.OCR for .NET provides the option to use spell-checking for result correction. For this, the API provides the [**RecognitionResult.GetSpellCheckCorrectedText**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/methods/getspellcheckcorrectedtext)  and [**RecognitionResult.GetSpellCheckErrorList**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/methods/getspellcheckerrorlist) methods.

The following code snippet demonstrates the use of the [**RecognitionResult.GetSpellCheckCorrectedText**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/methods/getspellcheckcorrectedtext)  method provides recognition result correction and [**RecognitionResult.GetSpellCheckErrorList**](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/methods/getspellcheckerrorlist) method gets a list with misspelled words and suggestions for correction

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Initialize an instance of AsposeOcr
	AsposeOcr api = new AsposeOcr();

	// Recognize image           
    RecognitionResult result = api.RecognizeImage(image, new RecognitionSettings());

    // Get result
	Console.WriteLine(result.RecognitionText);

	// Get corrected result
	string correctedResult = result.GetSpellCheckCorrectedText(SpellCheckLanguage.En);
	Console.WriteLine(correctedResult);

	//Get list of misspelled words with suggestions
	List<SpellCheckError> errorsList = result.GetSpellCheckErrorList(SpellCheckLanguage.En);
	foreach (var word in errorsList)
	{
		Console.Write(word.Word);
		Console.Write(word.StartPosition);
		Console.Write(word.Length);

		foreach (var suggest in word.SuggestedWords)
		{
			Console.Write(suggest.Word + " ");
		}
		Console.WriteLine();
	}
	
	Console.WriteLine(api.CorrectSpelling("recogniition"));
{{< /highlight >}}


