---
title: Recognize multipage DJVU
type: docs
weight: 31
url: /net/recognize-multipage-djvu/
aliases:
    - /net/recognize-multipage-djvu/
---

## Recognize multipage DJVU

Aspose.OCR provides the [**RecognizeDjvu**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizedjvu/ ) method that can recognize text on the images extracted from DJVU files. 
The [**RecognizeDjvu**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizedjvu/ ) method 
takes the DJVU path as a parameter and DocumentRecognitionSettings object. 
The following code snippet demonstrates the use of the [**RecognizeDjvu**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizedjvu/ ) method to recognize images from 
multipage DJVU file.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the DJVU file
	string dataDir = RunExamples.GetDataDir_OCR();

	// Archive Path
	string fullPath = dataDir + "OCR.djvu";

	// Recognize images from DJVU           
	DocumentRecognitionSettings set = new DocumentRecognitionSettings();
            set.PagesNumber = 0;// all pages
    List<RecognitionResult> result = api.RecognizeDjvu(imgPath, set);

	// Print result
	int pageNumber = 0;
    foreach (var page in result)
    {                
        System.Console.WriteLine($"Page: {pageNumber++} text: {page.RecognitionText}");
    }
```

