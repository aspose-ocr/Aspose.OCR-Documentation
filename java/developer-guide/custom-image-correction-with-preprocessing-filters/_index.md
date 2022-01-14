---
title: Custom Image Correction Using Preprocessing Filters
type: docs
weight: 30
url: /java/custom-image-correction-with-preprocessing-filters/
---

## **Custom Image Correction Preprocessing Filters**

Aspose.OCR for Java provides to option to specify custom preprocessing operations for image quality correction. 
For this, the API provides the [**RecognitionSettings.setPreprocessingFilters**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setPreprocessingFilters-com.aspose.ocr.PreprocessingFilter-) method. 
You can pass the instance of the [**RecognitionSettings**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class to the [**RecognizePage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage) method of the [**AsposeOCR**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

The following code snippet demonstrates the use of the [**PreprocessingFilters**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter) provides custom image quality correction. 
Usually, preprocessing operations done automatically, but in some cases, using [**PreprocessingFilters**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/PreprocessingFilter) you can get a better recognition result.
You can customize preprocessing operations directly in method [**RecognizePage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage)  or before recognitionprocess using [**PreprocessImage**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#PreprocessImage-java.lang.String-com.aspose.ocr.PreprocessingFilter-) method.

## Sample Code

{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = Utils.getSharedDataDir(PerformOCROnPage.class);

	// The image path
	String imagePath = dataDir + "p3.jpg";

	 // Create api instance
        AsposeOCR api = new AsposeOCR();
		
	    // settings object 
		RecognitionSettings set = new RecognitionSettings();
		
		// Preprocessing filters
		
		// filters object
		PreprocessingFilter filters = new PreprocessingFilter();
		// add filters as you need
		filters.add(PreprocessingFilter.ToGrayscale());
		filters.add(PreprocessingFilter.Rotate(-20));
		filters.add(PreprocessingFilter.Scale(2f));
		filters.add(PreprocessingFilter.Invert());
		filters.add(PreprocessingFilter.Resize(500,500));
		filters.add(PreprocessingFilter.Threshold(120));
		filters.add(PreprocessingFilter.BinarizeAndDilate());
		filters.add(PreprocessingFilter.ContrastCorrection());
		filters.add(PreprocessingFilter.Median());
		
		// Case 1. Preprocess image
		BufferedImage imageRes = api.PreprocessImage(imagePath, filters);
		// save the result
		File outputSource = new File("result.png");
		ImageIO.write(imageRes, "png", outputSource);
		// recognize optimized image
		RecognitionResult result = api.RecognizePage(imageRes, set);	
		// Print result
		printResult(result);

		// Case 2. Recognize image with filters
		set.setPreprocessingFilters(filters);
		result = api.RecognizePage(imagePath, set);	
		// Print result
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


