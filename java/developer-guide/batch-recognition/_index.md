---
title: Recognize multi images
type: docs
weight: 70
url: /java/batch-recognition/
---

## **Recognize archive**

Aspose.OCR for Java provides the method [**RecognizeMultiplePages**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizeMultiplePages-java.lang.String-com.aspose.ocr.RecognitionSettings-) that allows to recognize a multi images with one call. 
The result you will get is ArrayList of the [**RecognitionResult**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/RecognitionResult) class.

The following code snippet demonstrates the use of the [**RecognizeMultiplePages**](https://apireference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizeMultiplePages-java.lang.String-com.aspose.ocr.RecognitionSettings-) method.

# Sample Code 

```csharp
	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	String dataDir = "";

	// Archive Path
	string fullPath = dataDir + "OCR.zip";

	// Recognize images           
	ArrayList<RecognitionResult> results = api.RecognizeMultiplePages(fullPath, new RecognitionSettings());

	// Print result
	for (int i = 0; i < results.size(); i++)
	{
		 System.out.println("Result: " + results.get(i).recognitionText);
	}
```

## **Recognize folder**

# Sample Code 

```csharp

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	string dataDir = "";

	// Folder Path
	string fullPath = dataDir + "OCR";

// Recognize images           
	ArrayList<RecognitionResult> results = api.RecognizeMultiplePages(fullPath, new RecognitionSettings());

	// Print result
	for (int i = 0; i < results.size(); i++)
	{
		 System.out.println("Result: " + results.get(i).recognitionText);
	}
```

## **Recognize list**

# Sample Code 

```csharp

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The path to the documents directory.
	{
	string dataDir = "";

		// Recognize images  
ArrayList<String> files = new ArrayList<String>();			
			files.add("1.jpg");
			files.add("2.png");
			files.add("3.png");		
		ArrayList<RecognitionResult> results = api.RecognizeMultiplePages(files, new RecognitionSettings());

		// Print result
	for (int i = 0; i < results.size(); i++)
	{
		 System.out.println("Result: " + results.get(i).recognitionText);
	}
	}
	
```
