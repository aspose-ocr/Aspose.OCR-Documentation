---
title: Spelling Correction
type: docs
weight: 20
url: /java/spelling-correction/
description: This article explains how to correct image recognition errors using Spell Checker with Aspose.OCR for Java.
---

## Supported Dictionaries

Aspose.OCR for Java is able to correct spelling for the following languages:
* English
* German
* Spanish
* French
* Italian
* Portuguese
* Czech
* Danish
* Dutch
* Estonian
* Finnish
* Latvian
* Lithuanian
* Polish
* Romanian
* Slovak
* Slovene
* Swedish

## Recognize Text on Image with Spelling Correction

Aspose.OCR for Java provides a spell checker to correct spelling errors in recognized text. 
You can specify the dictionary that will be used for spelling correction. The following code shows how to get corrected text from an image using Java:


```csharp
public static void RecognizeAndSpellCheck()
{
    // Path to the image to recognize
    String imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOCR api = new AsposeOCR();
    
    // Recognize image           
    RecognitionResult result = api.RecognizePage(imagePath, new RecognitionSettings());
	System.out.println("Result: " + result.recognitionText);
    // Get corrected result
    String correctedResult = result.GetSpellCheckCorrectedText(SpellCheckLanguage.Eng);

	System.out.println("Result: " + correctedResult);
}
```

## Save Recognized Text with Corrected Spelling

Another way to correct errors in the recognition result is to apply spelling correction when saving the results.

```csharp
public static void RecognizeAndSaveCorrectedText()
{
    // Path to the image to recognize
    String imagePath =  "MyImage.jpg";
    String resultPath = "MyResult.docx";

    // Create OCR API
    AsposeOCR api = new AsposeOCR();
    
    // Recognize image and save the corrected text
    RecognitionResult result = api.RecognizePage(imagePath, new RecognitionSettings());
    result.save(resultPath, Format.Docx, SpellCheckLanguage.Eng);
}
```


## Get the List of Mispelled Words and Correction Suggestions 

The following code sample demonstrates how to get the list of misspelled words and suggested corrections.

```csharp
public static void RecognizeAndGetErrors()
{
    // Path to the image to recognize
    String imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOCR api = new AsposeOCR();

    // Recognize image           
    RecognitionResult result = api.RecognizePage(imagePath, new RecognitionSettings());

    //Get list of misspelled words with suggestions
    List<SpellCheckError> errorsList = result.getSpellCheckErrorList(SpellCheckLanguage.Eng);

    for(SpellCheckError error: errorsList) {
    {
        System.out.print($"Misspelled Word - {error.word}");
        System.out.print("Suggested words:");
       for(SuggestedWord w: error.suggestedWords) {
					System.out.print("suggested word:   " + w.word + "\n");
				}

        System.out.println();
    }
}
```

## Run Spell Check on Custom Text

It is also possible to perform Spell Check on any custom string as shown in the following snippet.

```csharp
public static void SpellCheck()
{
    // Text for spell check
    String textToCorrect = "Text wth errrors";

    // Create OCR API
     AsposeOCR api = new AsposeOCR();

    // Run Spell Check to correct errors
    String correctedText = api.correctSpelling(textToCorrect, SpellCheckLanguage.Eng);
    System.out.println(correctedText);
}
```

## Upload own dictionary

It is also possible to upload frequency dictionary as shown in the following snippet.

Dictionary file format:
 - Dictionary file format:
 - Plain text file in UTF-8 encoding.
 - Word and Word Frequency are separated by comma, the word is expected in the first column and the frequency in the second column.
 - Every word-frequency-pair in a separate line.A line is defined as a sequence of characters followed by a line feed ("\n"), a carriage return ("\r"), 
 - or a carriage return immediately followed by a line feed("\r\n").
 - Every word is expected to be in lower case.


```csharp
public static void SpellCheck()
{
   // Path to the image to recognize
    String imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOCR api = new AsposeOCR();

    // Recognize image           
    RecognitionResult result = api.RecognizePage("img.png", new RecognitionSettings());
	
	// Path to the dictionary
	String dictionaryPath = $"dictionary.txt";
	// Run Spell Check to correct errors
	result.useUserDictionary(dictionaryPath);
	String corrected = res.getSpellCheckCorrectedText(SpellCheckLanguage.Eng)
	Console.WriteLine(corrected);
}
```