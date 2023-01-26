---
weight: 110
date: "2023-01-17"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/car-plate/
feedback: OCRNET
title: Extracting text from vehicle license plate images
description: How to automatically extract text from scanned or photographed vehicle license plates.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- vehicle
- license plate
- car plate
- number
---

Aspose.OCR offers a special recognition algorithm that extracts text from vehicle license plates, including dark and blurry photos. The resulting text can then be automatically saved to the database or automatically verified.

To extract text from a vehicle license plate image, use [`RecognizeCarPlate`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizecarplate/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-car-plate/).

The method returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the vehicle license plate text and other details.

{{< tabs tabID="1" tabTotal="2" tabName1="Read vehicle license plate from path" tabName2="Read vehicle license plate from memory" >}}
{{< tab tabNum="1" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.CarPlateRecognitionSettings recognitionSettings = new Aspose.OCR.CarPlateRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeCarPlate("car-plate.png", recognitionSettings);
Console.WriteLine(result.RecognitionText);
```
{{< /tab >}}
{{< tab tabNum="2" >}}
```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
Aspose.OCR.CarPlateRecognitionSettings recognitionSettings = new Aspose.OCR.CarPlateRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
using(MemoryStream ms = new MemoryStream())
{
	using(FileStream fs = new FileStream("car-plate.png", FileMode.Open, FileAccess.Read))
	{
		fs.CopyTo(ms);
		Aspose.OCR.RecognitionResult result = recognitionEngine.RecognizeCarPlate(ms, recognitionSettings);
		Console.WriteLine(result.RecognitionText);
	}
}
```
{{< /tab >}}
{{< /tabs >}}
