---
title: Multithreading support in recognition
type: docs
weight: 75
url: /java/multithreading-support-in-recognition/
---
## **Multithreading support in recognition**
Aspose.OCR for Java provides to option to specify threads count value to increase performance. 
For this, the API provides the [**RecognitionSettings.setThreadsCount**](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setThreadsCount-int-) property. 
You can pass the instance of the [**RecognitionSettings**](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings) class to the [**RecognizePage**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR#RecognizePage-java.lang.String-com.aspose.ocr.RecognitionSettings-) method 
of the [**AsposeOCR**](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

The following code snippet demonstrates the use of the [**setThreadsCount**](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setThreadsCount-int-) property provides custom number of threads. 
ThreadsCount by default equals customer processors number, but using [**setThreadsCount**](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setThreadsCount-int-) property can get better perfomance. You can customize it from 0. 
If you set  the [**setThreadsCount**](https://reference.aspose.com/ocr/java/com.aspose.ocr/RecognitionSettings#setThreadsCount-int-) as 0 (zero), this value will be calculated automatically and equal to the number of cores of your processor..


## Sample Code


{{< highlight csharp >}}
...

	// For complete examples and data files, please go to https://github.com/aspose-ocr/Aspose.OCR-for-Java
	// The image path
	String imagePath = "0001460985.Jpeg";

	// case 1
	//Create api instance
	AsposeOCR api = new AsposeOCR();

	try {
	RecognitionSettings set = new RecognitionSettings();
	set.setThreadsCount(2);
		RecognitionResult result = api.RecognizePage(imagePath);
		System.out.println("File: " + imagePath);
		System.out.println("Result: " + result.recognitionText);
	} catch (IOException e) {
		e.printStackTrace();
	}
	
{{< /highlight >}}

