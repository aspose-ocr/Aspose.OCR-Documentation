---
title: Recognize scanned PDF
type: docs
weight: 30
url: /java/recognize-scanned-pdf/
---

Recognize scanned PDF

Aspose.OCR for Java provides the [**RecognizePdf**](https://apireference.aspose.com/ocr/java/com.aspose.ocr.pdf/AsposeOCRPdf) method that can recognize text on the images extracted from scanned PDF files. 
The [**RecognizePdf**](https://apireference.aspose.com/ocr/java/com.aspose.ocr.pdf/AsposeOCRPdf) method takes the PDF path as a parameter and DocomentRecognitionSettings object.
You have to set the number of pages for recognition in the [**DocomentRecognitionSettings**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/DocumentRecognitionSettings) constructor or using setter. 0 means all pages will recognize. 
The following code snippet demonstrates the use of the [**RecognizePdf**](https://apireference.aspose.com/ocr/java/com.aspose.ocr.pdf/AsposeOCRPdf) method to recognize images from scanned multipage PDF file.

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = Utils.getSharedDataDir(PerformOCROnPage.class);

	// The image path
	String imagePath = dataDir + "p3.pdf";

	// Initialize an instance of AsposeOcr
	 AsposeOCRPdf api = new AsposeOCRPdf();

        // Set license 
        License.setLicense("Aspose.Total.lic");
        
        // Get PDF file for recognize     
        String imgPath = p.pdf";

       // settings (set the pages amount in constructor). 
		DocumentRecognitionSettings set = new DocumentRecognitionSettings(1);
		set.setStartPage(2);
		
		// Recognize images from PDF 
		ArrayList<RecognitionResult> result = api.RecognizePdf(imgPath, set);
		
		// result
		for(RecognitionResult page : result) {
			System.out.print("PAGE: ");
			printResult(page);
		}
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


