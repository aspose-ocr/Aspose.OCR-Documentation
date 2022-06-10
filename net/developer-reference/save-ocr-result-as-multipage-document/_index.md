---
title: Save ocr result as multipage document
type: docs
weight: 30
url: /net/save-ocr-result-as-multipage-document/
aliases:
    - /net/save-ocr-result-as-multipage-document/
---

## Recognize scanned PDF and save Searchable PDF (or DOCX)

Aspose.OCR provides the [**SaveMultipageDocument**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/savemultipagedocument) method that can save List<RecognitionResult> into Rearchable PDF or DOCX file.
The [**SaveMultipageDocument**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/savemultipagedocument) method 
takes the output path as a parameter, file format and List<RecognitionResult> objects. 
The following code snippet demonstrates the use of the [**SaveMultipageDocument**](https://apireference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/savemultipagedocument) method.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the PDF file
	string dataDir = RunExamples.GetDataDir_OCR();

	// Scanned multipage PDF Path
	string fullPath = dataDir + "OCR.pdf";
	
	// Get API
    AsposeOcr api = new AsposeOcr();

	//Recognize images from PDF           
	List<RecognitionResult> res1 = api.RecognizePdf(fullPath, new DocumentRecognitionSettings
            {
                ThreadsCount = 1,
                StartPage = 0,
                PagesNumber = 2
            });

	//Save result as Searchable PDF
    AsposeOcr.SaveMultipageDocument("D://imgs/test/net.pdf", SaveFormat.Pdf, res1);
	
	// Archive Path
	string fullPath = dataDir + "OCR.zip";
	
	//Recognize images from zip           
	RecognitionResult[] res2 = api.RecognizeMultipleImages(@"test.zip", new RecognitionSettings());

	//Save result as DOCX
    AsposeOcr.SaveMultipageDocument("D://imgs/test/net.docx", SaveFormat.Docx, res2.ToList());
```

