---
title: Result correction with spell-checking
type: docs
weight: 75
url: /java/result-correction-with-spell-checking/
---
## **Result correction with spell-checking**
Aspose.OCR for Java provides the option to use spell-checking for result correction. For this, the API provides the [**RecognitionResult.getSpellCheckCorrectedText**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#getSpellCheckCorrectedText--)  
and [**RecognitionResult.getSpellCheckErrorList**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#getSpellCheckErrorList--) methods.

The following code snippet demonstrates the use of the [**RecognitionResult.getSpellCheckCorrectedText**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#getSpellCheckCorrectedText--)   method provides recognition result correction and [**RecognitionResult.getSpellCheckErrorList**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult#getSpellCheckErrorList--) method 
gets a list with misspelled words and suggestions for correction (List<SpellCheckError>).

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	string dataDir = "";

	// Initialize an instance of AsposeOcr
	AsposeOCR api = new AsposeOCR();

	// Recognize image           
    RecognitionResult result = api.RecognizePage(image, new RecognitionSettings());

    // Get result
	System.out.println("Result: " + result.recognitionText);

	// Get corrected result
	String correctedResult = result.getSpellCheckCorrectedText(SpellCheckLanguage.Eng);
	System.out.println("Result: " + correctedResult);

	//Get list of misspelled words with suggestions
	List<SpellCheckError> errorsList = result.GetSpellCheckErrorList(SpellCheckLanguage.En);
	for(SpellCheckError error: list) {
				System.out.print("error:   " + error.word+ "\n");
				System.out.print("error:   " + error.startPosition+ "\n");
				System.out.print("error:   " + error.length+ "\n");
				for(SuggestedWord w: error.suggestedWords) {
					System.out.print("suggested word:   " + w.word + "\n");
				}
		}
		Console.WriteLine();
	}
	
	System.out.print(api.CorrectSpelling("recogniition", SpellCheckLanguage.Eng));
{{< /highlight >}}


