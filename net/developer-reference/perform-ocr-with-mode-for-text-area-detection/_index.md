---
title: Perform OCR with different modes for automatic text area detection
type: docs
weight: 72
url: /net/perform-ocr-with-mode-for-text-area-detectionn/
---

## **Perform OCR with different mode for automatic text area detection**

Aspose.OCR for .NET provides the enum [**DetectAreasMode**](https://apireference.aspose.com/ocr/net/aspose.ocr/detectareasmode ) that allows to set mode for text regions detection.
The [**RecognitionSettings**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings ) class contains property that allows to set [**DetectAreasMode**](https://apireference.aspose.com/ocr/net/aspose.ocr/recognitionsettings/properties/detectareasmode )

The following code snippet demonstrates the use of the [**DetectAreasMode**](https://apireference.aspose.com/ocr/net/aspose.ocr/detectareasmode ) enum.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Archive Path
	string fullPath = dataDir + "OCR.img";

	// Recognize images           
	RecognitionSettings set = new RecognitionSettings 
            { 
                DetectAreasMode = DetectAreasMode.PHOTO, 
                LinesFiltration = false, 
                ThreadsCount = 1, 
                DetectAreas = true, 
                AutoSkew = true, 
                Language = Language.None 
            };
    var result = api.RecognizeImage(fullPath, set);

	// Print result
	Console.WriteLine($"Result:\n {result.RecognitionText}");
```
