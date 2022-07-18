---
title: Save ocr result as multipage document
type: docs
weight: 30
url: /java/save-ocr-result-as-multipage-document/
---

## **Recognize scanned PDF and save Searchable PDF (or DOCX)**
## **Recognize list of images and save Searchable PDF (or DOCX)**

Aspose.OCR provides the [**SaveMultipageDocument**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#SaveMultipageDocument-java.lang.String-com.aspose.ocr.Format-java.util.ArrayList-) 
method that can save ArrayList<RecognitionResult> into Rearchable PDF or DOCX file.
The [**SaveMultipageDocument**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#SaveMultipageDocument-java.lang.String-com.aspose.ocr.Format-java.util.ArrayList-) method 
takes the output path as a parameter, file format and ArrayList<RecognitionResult> objects. 
The following code snippet demonstrates the use of the [**SaveMultipageDocument**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#SaveMultipageDocument-java.lang.String-com.aspose.ocr.Format-java.util.ArrayList-) method.

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = Utils.getSharedDataDir(PerformOCROnPage.class);

	

	// recognize the list of images and save as multi-page Searchable PDF
	// Create api instance
    AsposeOCR api = new AsposeOCR();		
	// settings object 
	RecognitionSettings set = new RecognitionSettings();
	ArrayList<String> files = new ArrayList<String>();
			files.add("fie1.bmp");
			files.add("fie2.jpg");
			files.add("fie3.png");
	ArrayList<RecognitionResult> results = api.RecognizeMultiplePages(files, set);
	//save result	
	AsposeOCR.SaveMultipageDocument("java.pdf", Format.Pdf, results);
		
	// recognize multi-page PDF and save as multi-page docx
	// The image path
	String imagePath = dataDir + "p3.jpg";
	// Create api instance
	AsposeOCRPdf apiPdf = new AsposeOCRPdf();
	// settings object 
	DocumentRecognitionSettings doc_set = new DocumentRecognitionSettings(2);//Set the number of pages for recognition multipage pdf file.
	ArrayList<RecognitionResult> result =  apiPdf.RecognizePdf("file.pdf", set); 	
	//save result	
	AsposeOCR.SaveMultipageDocument("java.docx", Format.Docx, result);
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


