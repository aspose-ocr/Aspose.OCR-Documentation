---
title: Recognize scanned PDF
type: docs
weight: 30
url: /net/recognize-scanned-pdf/
aliases:
    - /net/recognize-scanned-pdf/
---

## Recognize scanned PDF

Aspose.OCR provides the [**RecognizePdf**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/calculateskew/methods/1) method that can recognize text on the images extracted from scanned PDF files. The [**RecognizePdf**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/calculateskew/methods/1) method takes the image path as a parameter and returns the skew angle. 
The following code snippet demonstrates the use of the [**RecognizePdf**](https://apireference.aspose.com/ocr/net/aspose.ocr.asposeocr/calculateskew/methods/1) method to recognize images from scanned multipage PDF file.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the PDF file
	string dataDir = RunExamples.GetDataDir_OCR();

	// Archive Path
	string fullPath = dataDir + "OCR.pdf";

	// Recognize images from PDF           
	DocumentRecognitionSettings set = new DocumentRecognitionSettings();
            set.DetectAreas = false;
    List<RecognitionResult> result = api.RecognizePdf(imgPath, set);

	// Print result
	int pageNumber = 0;
    foreach (var page in result)
    {                
        System.Console.WriteLine($"Page: {pageNumber++} text: {page.RecognitionText}");
    }
```

