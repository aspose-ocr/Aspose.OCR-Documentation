---
weight: 10
date: "2023-08-30"
author: "Vladimir Lapin"
type: docs
url: /python-net/recognition/id-card/
feedback: OCRPYNET
title: Extracting text from ID cards
description: How to digitize scanned or photographed ID cards by automatically extracting text from them.
keywords:
- read
- extract
- OCR
- recognize
- check
- image
- photo
- ID
- card
---

An identity card (commonly abbreviated as _ID_) is a small plastic or paper card that is used to verify a person's identity. This can be an identity card, work permit, residence permit, passport card or other identity document. Manually re-typing text from ID cards, especially in batch mode, is time consuming and commonly leads to errors.

Aspose.OCR for Python via .NET offers a special recognition algorithm that extracts text from scanned or photographed ID cards, which can then be automatically saved to the database or automatically verified. To extract text from an ID card, use `recognize_id_card()` method of [`AsposeOcr`](https://reference.aspose.com/ocr/python-net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/python-net/recognition-settings-id-card/).

The method takes [`OcrInput` object](/ocr/python-net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/python-net/aspose.ocr/recognitionresult/) object containing the identity data.

```python
# Instantiate Aspose.OCR API
api = AsposeOcr()
# Add image to the recognition batch
input = OcrInput(InputType.SINGLE_IMAGE)
input.add("ID1.png")
input.add("ID2.png")
# Set recognition language
recognitionSettings = IDCardRecognitionSettings()
recognitionSettings.Language = Aspose.OCR.Language.Latin;
# Recognize ID cards
results = api.recognize_id_card(input, recognitionSettings)
# Print recognition result
for result in results:
    print(result.recognition_text)
```
