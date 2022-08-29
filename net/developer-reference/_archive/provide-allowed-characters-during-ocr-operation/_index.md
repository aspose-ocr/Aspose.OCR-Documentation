---
title: Provide allowed characters during OCR operation
type: docs
weight: 60
url: /net/provide-allowed-characters-during-ocr-operation/
---

## **Provide allowed characters during OCR operation**
In case you know the characters that are present in the image, you can pass those characters while instantiating the [AsposeOCR](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr) class. Doing this will ensure that only the provided characters are matched in the OCR process. The following code snippet demonstrates setting the allowed characters for the OCR process.

{{< gist "aspose-com-gists" "dad6b4a35169ed7893fd376e819d7626" "Examples-CSharp-PerformingandManagingOCR-SpecifyAllowedCharacters-1.cs" >}}

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
// The path to the documents directory.
string dataDir = RunExamples.GetDataDir_OCR();

// case 1
// Initialize an instance of AsposeOcr with allowed symbols
AsposeOcr api = new AsposeOcr("0123456789");

// Recognize image
string result = api.RecognizeLine(dataDir + "0001460985.Jpeg");

// Display the recognized text
Console.WriteLine(result);

// case 2
var res = api.RecognizeImage(dataDir + "0001460985.Jpeg", new RecognitionSettings { AllowedCharacters = CharactersAllowedType.LATIN_ALPHABET });
// Display the recognized text
Console.WriteLine(res.RecognitionText);           
	
	
{{< /highlight >}}
