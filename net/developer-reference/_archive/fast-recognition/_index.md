---
title: Fast recognition
type: docs
weight: 71
url: /net/fast-recognition/
---

## **Recognize without skew correction and areas detection**

Aspose.OCR for .NET provides the method [**RecognizeImageFast**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) 
 that allows to recognize images in fastest mode. 

The following code snippet demonstrates the use of the [**RecognizeImageFast**](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/methods/recognizemultipleimages) method.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-.NET
	// The path to the documents directory.
	string dataDir = RunExamples.GetDataDir_OCR();

	// Get image for recognize
    string image = dataDir + "img.jpg";

    // Recognize image without skew correction and areas detection. Uses Latin alphabet. The fastest mode.  
    string result = api.RecognizeImageFast(image);			
			
	// Print result
	Console.WriteLine(result);
```
