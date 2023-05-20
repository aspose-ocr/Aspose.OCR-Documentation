---
weight: 30
date: "2023-05-19"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/car-plate/
feedback: OCRJAVA
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

To extract text from a vehicle license plate image, use `RecognizeCarPlate` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-car-plate/).

The method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a list of recognition results containing the vehicle license plate text and other details.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "car1.png"));
input.add(os.path.join(self.dataDir, "car2.png"));
// Recognition settings
CarPlateRecognitionSettings recognitionSettings = new CarPlateRecognitionSettings();
recognitionSettings.setIgnoredCharacters("Ää");
// Recognize license plates
results = api.RecognizeCarPlate(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
