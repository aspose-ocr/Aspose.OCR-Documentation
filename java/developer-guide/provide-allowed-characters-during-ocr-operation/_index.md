---
title: Provide allowed characters during OCR operation
type: docs
weight: 50
url: /java/provide-allowed-characters-during-ocr-operation/
---

## **Provide allowed characters during OCR operation**
In case you know the characters that are present in the image, you can pass those characters while instantiating the [AsposeOCR](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class. Doing this will ensure that only the provided characters are matched in the OCR process. The following code snippet demonstrates setting the allowed characters for the OCR process.


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
	AsposeOCR api = new AsposeOCR("123456789");

	try {
		String result = api.RecognizeLine(imagePath);
		System.out.println("File: " + imagePath);
		System.out.println("Result line: " + result);
	} catch (IOException e) {
		e.printStackTrace();
	}
	
	// case 2
	//Create api instance
	AsposeOCR api2 = new AsposeOCR();

	try {
		RecognitionSettings settings = new RecognitionSettings();
		settings.setAllowedCharacters(CharactersAllowedType.DIGITS);
		RecognitionResult result = api2.RecognizePage(imagePath.getFile(), settings);
		System.out.println("File: " + imagePath);
		System.out.println("Result: " + result);
	} catch (IOException e) {
		e.printStackTrace();
	}
	
	
{{< /highlight >}}

