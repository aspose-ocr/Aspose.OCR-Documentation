---
title: Fast recognition
type: docs
weight: 70
url: /java/fast-recognition/
---

## **Recognize without skew correction and areas detection**

Aspose.OCR for Java provides the method [**RecognizePageFast**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizeMultiplePages-java.lang.String-com.aspose.ocr.RecognitionSettings-) that allows to recognize images in fastest mode. 
The result you will get is String.

The following code snippet demonstrates the use of the [**RecognizePageFast**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizeMultiplePages-java.lang.String-com.aspose.ocr.RecognitionSettings-) method.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = "";

	// Archive Path
	string fullPath = dataDir + "OCR.jpg";

	// Recognize images           
	String result = api.RecognizePageFast(file); // without skew correction and areas detection

	// Print result
	out.println("result:" + result); 
```

