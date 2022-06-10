---
title: Recognize multipage TIFF
type: docs
weight: 31
url: /net/recognize-multipage-tiff/
aliases:
    - /net/recognize-multipage-tiff/
---

## Recognize multipage TIFF

Aspose.OCR provides the [**RecognizeTiff**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizetiff) method that can recognize text on the images extracted from TIFF files. 
The [**RecognizeTiff**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizetiff) method 
takes the TIFF path as a parameter and DocumentRecognitionSettings object. 
The following code snippet demonstrates the use of the [**RecognizeTIFF**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizetiff) method to recognize images from 
multipage TIFF(TIF) file.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the TIFF file
	string dataDir = RunExamples.GetDataDir_OCR();

	// Archive Path
	string fullPath = dataDir + "OCR.tiff";

	// Recognize images from TIFF           
	DocumentRecognitionSettings set = new DocumentRecognitionSettings();
            set.PagesNumber = 0;// all pages
    List<RecognitionResult> result = api.RecognizeTiff(imgPath, set);

	// Print result
	int pageNumber = 0;
    foreach (var page in result)
    {                
        System.Console.WriteLine($"Page: {pageNumber++} text: {page.RecognitionText}");
    }
```

