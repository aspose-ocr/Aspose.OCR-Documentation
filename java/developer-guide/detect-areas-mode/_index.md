---
title: Detect Areas Mode
type: docs
weight: 80
url: /java/detect-areas-mode/
---

## **Detect Areas Mode**

Aspose.OCR for Java provides to option to specify the area recognition method. 
For this, the API provides the [**DetectAreasMode **](https://apireference.aspose.com/ocr/java/com.aspose.ocr/DetectAreasMode) enum. 
You can set the property of DetectAreasMode in the method [**setDetectAreasMode**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setDetectAreasMode) in the [**RecognitionSettings**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) and pass the instanse of it 
to the [**RecognizePage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage) 
method of the [**AsposeOCR**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

The following code snippet demonstrates the use of the DetectAreasMode  method. 
You can disable regions detection and use DetectAreasMode.NONE, or you can choose the best region detection method according to placing text on your image. 
So in some cases, using [**DetectAreasMode **](https://apireference.aspose.com/ocr/java/com.aspose.ocr/DetectAreasMode) you can get a better recognition result.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
		// The path to the documents directory.
		String dataDir = "";

		// The image path
		String file = dataDir + "Receipt.jpg";

		//Create api instance
		AsposeOCR api = new AsposeOCR();

		// set recognition options
		RecognitionSettings settings = new RecognitionSettings();
		settings.setDetectAreasMode(DetectAreasMode.PHOTO);

		// get result object
		RecognitionResult result = null;
		try {
			result = api.RecognizePage(file, settings);
		} catch (IOException e) {
			e.printStackTrace();
		}

		// print result
		printResult(result);
		// ExEnd:1

		System.out.println("OCROperationWithDetectAreasMode: execution complete");
	
	
	static void printResult(RecognitionResult result) {
		//TEXT
		System.out.println("TEXT:\n" + result.recognitionText);
		
		//SKEW
		System.out.print("SKEW: ");
		System.out.println(result.skew);
		
		//PARAGRAPHS
		System.out.println("\nPARAGRAPHS:");    	
		for (String paragraph : result.recognitionAreasText){
			System.out.println(paragraph);
		}
		
		//PARAGRAPHS COORDS
		System.out.println("PARAGRAPHS COORDS:");
		for (Rectangle rectangle : result.recognitionAreasRectangles){
			System.out.println("X: " + rectangle.x + "Y: " + rectangle.y + "Width: " + rectangle.width + "Height: " + rectangle.height);
		}
		
		//LINES
		System.out.println("LINES:");
		for (LinesResult line : result.recognitionLinesResult){
			if(line.line != null) {
			System.out.print("X: " + line.line.x + "Y: " + line.line.y + "Width: " + line.line.width + "Height: " + line.line.height);
			System.out.println(" " + line.textInLine);
			}
		}
		
		//POSSIBLE CHOICES FOR CHARACTERS
		System.out.println("POSSIBLE CHOICES FOR CHARACTERS:");
		for (char[] choices : result.recognitionCharactersList){
			if(choices != null) {
			System.out.println("character: " + choices[0] + " " + choices[1] + " " + choices[2] + " " + choices[3] + " " + choices[4]);
			}
		}    	
		
		//WARNINGS
		System.out.println("WARNINGS:");
		for (String warning : result.warnings){
			System.out.print(warning);
		}
		
		//JSON
		System.out.println("JSON:");
		System.out.print(result.GetJson());
		
		//SPELL-CHECK CORRECTED TEXT
		System.out.println("SPELL-CHECK CORRECTED TEXT:");
		System.out.print(result.getSpellCheckCorrectedText());
	}
```
