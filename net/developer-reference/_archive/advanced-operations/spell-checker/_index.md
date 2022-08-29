---
title: Spelling Correction
type: docs
weight: 20
url: /net/spelling-correction/
description: This article explains how to correct image recognition errors using Spell Checker with Aspose.OCR for .NET.
---

## Supported Dictionaries

Aspose.OCR for .NET is able to correct spelling for the following languages:
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

Aspose.OCR for .NET provides a spell checker to correct spelling errors in recognized text. You can specify the dictionary that will be used for spelling correction. The following code shows how to get corrected text from an image using C#:


```csharp
public static void RecognizeAndSpellCheck()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();
    
    // Recognize image           
    RecognitionResult result = api.RecognizeImage(imagePath, new RecognitionSettings());

    // Get corrected result
    string correctedResult = result.GetSpellCheckCorrectedText(SpellCheckLanguage.Eng);

    Console.WriteLine(correctedResult);
}
```

## Save Recognized Text with Corrected Spelling

Another way to correct errors in the recognition result is to apply spelling correction when saving the results.

```csharp
public static void RecognizeAndSaveCorrectedText()
{
    // Path to the image to recognize
    string imagePath =  "MyImage.jpg";
    string resultPath = "MyResult.txt";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();
    
    // Recognize image and save the corrected text
    RecognitionResult result = api.RecognizeImage(imagePath, new RecognitionSettings());
    result.Save(resultPath, true, SpellCheckLanguage.Eng);
}
```


## Get the List of Mispelled Words and Correction Suggestions 

The following code sample demonstrates how to get the list of misspelled words and suggested corrections.

```csharp
public static void RecognizeAndGetErrors()
{
    // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();

    // Recognize image           
    RecognitionResult result = api.RecognizeImage(imagePath, new RecognitionSettings());

    //Get list of misspelled words with suggestions
    List<SpellCheckError> errorsList = result.GetSpellCheckErrorList(SpellCheckLanguage.Eng);

    foreach (var word in errorsList)
    {
        Console.WriteLine($"Misspelled Word - {word.Word}");
        Console.WriteLine("Suggested words:");
        foreach (var suggest in word.SuggestedWords)
        {
            Console.Write(suggest.Word + " ");
        }

        Console.WriteLine();
    }
}
```

## Run Spell Check on Custom Text

It is also possible to perform Spell Check on any custom string as shown in the following snippet.

```csharp
public static void SpellCheck()
{
    // Text for spell check
    string textToCorrect = "Text wth errrors";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();

    // Run Spell Check to correct errors
    string correctedText = api.CorrectSpelling(textToCorrect, SpellCheckLanguage.Eng);
    Console.WriteLine(correctedText);
}
```

## Upload own dictionary

It is also possible to upload frequency dictionary as shown in the following snippet.

Dictionary file format:
- Plain text file in UTF-8 encoding.
- Word and Word Frequency are separated by space or tab.Per default, the word is expected in the first column and the frequency in the second column.
- Every word-frequency-pair in a separate line.A line is defined as a sequence of characters followed by a line feed ("\n"), a carriage return ("\r"), 
or a carriage return immediately followed by a line feed("\r\n").
- Every word is expected to be in lower case.

```csharp
public static void SpellCheck()
{
   // Path to the image to recognize
    string imagePath = "MyImage.jpg";

    // Create OCR API
    AsposeOcr api = new AsposeOcr();

    // Recognize image           
    RecognitionResult res = api.RecognizeImage("img.png", new RecognitionSettings());
	
	// Path to the dictionary
	string dictionaryPath = $"dictionary.txt";
	// Run Spell Check to correct errors
	string corrected = res.GetSpellCheckCorrectedText(SpellCheckLanguage.Eng, dictionaryPath)
	Console.WriteLine(corrected);
}
```