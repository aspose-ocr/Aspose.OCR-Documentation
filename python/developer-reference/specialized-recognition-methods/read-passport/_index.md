---
weight: 20
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition/passport/
feedback: OCRPYNET
title: Extracting text from passport images
description: How to digitize scanned or photographed passports by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- passport
---

Automatic passport recognition and verification is a very common task in many areas: border control, banking, security, and so on. However, manually re-typing text is an error-prone and time-consuming process, and mistakes can lead to security breaches and other undesirable consequences.

Aspose.OCR for Python via .NET offers a special recognition algorithm that extracts text from scanned or photographed passports, which can then be automatically saved to the database or automatically verified.

To extract text from a passport image, use `recognize_passport()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-passport/).

The method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object containing the passport data.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("passport1.png")
input.add("passport2.png")
# Set recognition language
recognitionSettings = PassportRecognitionSettings()
recognitionSettings.Language = Aspose.OCR.Language.Latin;
# Recognize passports
results = api.recognize_passport(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```
