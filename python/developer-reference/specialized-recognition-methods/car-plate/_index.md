---
weight: 30
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
ai_search_scope: ocr_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
url: /python-net/recognition/car-plate/
feedback: OCRPYNET
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

Aspose.OCR for Python via .NET offers a special recognition algorithm that extracts text from vehicle license plates, including dark and blurry photos. The resulting text can then be automatically saved to the database or automatically verified.

To extract text from a vehicle license plate image, use `recognize_car_plate()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-car-plate/).

The method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns `OcrOutput` object containing the vehicle license plate text and other details.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("car1.png")
input.add("car2.png")
# Set recognition language
recognitionSettings = CarPlateRecognitionSettings()
recognitionSettings.Language = Aspose.OCR.Language.Latin;
# Recognize license plates
results = api.recognize_car_plate(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```
