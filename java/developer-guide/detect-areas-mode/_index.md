---
title: Detect Areas Mode
type: docs
weight: 80
url: /java/detect-areas-mode/
---

Aspose.OCR for Java allows you to explicitly specify the region recognition method. This can improve recognition results if you know the type of content in the image.

OCR API provides [`DetectAreasMode`](https://reference.aspose.com/ocr/java/com.aspose.ocr/DetectAreasMode) enumerator with the following constants:

- `NONE` - disable regions detection;
- `DOCUMENT` - detect paragraphs with a machine learning model trained on documents;
- `PHOTO` - detect paragraphs with a machine learning model trained on photos;
- `TABLE` - detect table cells;
- `COMBINE` - detect paragraphs with text and then detect regions inside paragraphs.

To choose the preferred region detection method, create an instance of [`RecognitionSettings`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class and pass one of the above-mentioned values in its [`setDetectAreasMode`](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setDetectAreasMode-com.aspose.ocr.DetectAreasMode-) method. Then pass the instance of `RecognitionSettings` class to [`RecognizePage`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage) method.

## Example

The following code snippet demonstrates how to specify the region recognition method. Visit https://github.com/aspose-ocr/Aspose.OCR-for-Java for the full project and sample data files.

```csharp
// The path to the documents directory
String dataDir = "";

// The image path
String file = dataDir + "Receipt.jpg";

// Create instance of OCR API
AsposeOCR api = new AsposeOCR();

// Set region recognition method
RecognitionSettings settings = new RecognitionSettings();
settings.setDetectAreasMode(DetectAreasMode.PHOTO);

// Get result object
RecognitionResult result = null;
try {
	result = api.RecognizePage(file, settings);
} catch (IOException e) {
	e.printStackTrace();
}

// Print result
printResult(result);

// Output result helper method
static void printResult(RecognitionResult result) {
	//TEXT
	System.out.println("TEXT:\n" + result.recognitionText);

	//SKEW
	System.out.print("SKEW: ");
	System.out.println(result.skew);

	//PARAGRAPHS
	System.out.println("PARAGRAPHS:");    	
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
