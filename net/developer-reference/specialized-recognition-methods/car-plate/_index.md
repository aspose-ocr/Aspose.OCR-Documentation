---
weight: 30
date: "2023-05-18"
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

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the vehicle license plate text and other details.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("car1.png");
input.Add("car2.png");
// Recognition settings
Aspose.OCR.CarPlateRecognitionSettings recognitionSettings = new Aspose.OCR.CarPlateRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize license plates
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizeCarPlate(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
