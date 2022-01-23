---
title: Provide ignored characters during OCR operation
type: docs
weight: 60
url: /java/provide-ignored-characters-during-ocr-operation/
---

## **Provide ignored characters during OCR operation**
In case you know the characters that aren't present in the image, you can pass those characters as a value for property 
[**RecognitionSettings.setIgnoredCharacters **](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setIgnoredCharacters-java.lang.String-). 
Doing this will ensure that the provided characters aren't matched in the OCR process. The following code snippet demonstrates setting the ignored characters for the OCR process.

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = Utils.getSharedDataDir(SpecifyAllowedCharacters.class);

	// The image path
	String imagePath = dataDir + "0001460985.Jpeg";

	// case 1
	//Create api instance
	AsposeOCR api = new AsposeOCR();

	try {
	RecognitionSettings set = new RecognitionSettings();
	set.setIgnoredCharacters("abcdefghijklmopqrstu");
		RecognitionResult result = api.RecognizePage(imagePath);
		System.out.println("File: " + imagePath);
		System.out.println("Result: " + result.recognitionText);
	} catch (IOException e) {
		e.printStackTrace();
	}
	
{{< /highlight >}}

