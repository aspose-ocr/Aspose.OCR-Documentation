---
title: RecognitionResult: get split lines with coordinates and with text
type: docs
weight: 30
url: /java/result-get-lines/
---

## **RecognitionResult: get split lines with coordinates and with text**
Aspose.OCR for Java provides the option to get the result as split lines [**RecognitionResult.LinesResult**](https://apireference.aspose.com/ocr/net/aspose.ocr.recognitionresult/linesresult). 
For this, the API provides the property[**RecognitionResult.RecognitionLinesResult**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionresult/properties/recognitionlinesresult).

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = Utils.getSharedDataDir(PerformOCROnPage.class);

	// The image path
	String imagePath = dataDir + "p3.png";

	// Initialize an instance of AsposeOcr
	 AsposeOCR api = new AsposeOCR();

        // Set license 
        License.setLicense("Aspose.Total.lic");
        
        // Get image file for recognize     
        String imgPath = p.txt";

        // settings
		RecognitionSettings set = new RecognitionSettings();
		
		// Recognize image
		RecognitionResult result = api.RecognizePage(imgPath, set);
		
		// result
		printResult(result);       
    }
    
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
    		System.out.print("X: " + line.line.x + "Y: " + line.line.y + "Width: " + line.line.width + "Height: " + line.line.height);
    		System.out.println(" " + line.textInLine);
    	}
    	
    	//POSSIBLE CHOICES FOR CHARACTERS
    	System.out.println("POSSIBLE CHOICES FOR CHARACTERS:");
    	for (char[] choices : result.recognitionCharactersList){
    		System.out.println("character: " + choices[0] + " " + choices[1] + " " + choices[2] + " " + choices[3] + " " + choices[4]);
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
{{< /highlight >}}


