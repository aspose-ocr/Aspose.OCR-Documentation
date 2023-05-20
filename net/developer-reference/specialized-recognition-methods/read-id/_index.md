---
weight: 10
date: "2023-05-18"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/id-card/
feedback: OCRNET
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

Aspose.OCR offers a special recognition algorithm that extracts text from scanned or photographed ID cards, which can then be automatically saved to the database or automatically verified.

To extract text from an ID card, use [`RecognizeIDCard`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizeidcard/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-id-card/).

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the identity data.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("ID1.png");
input.Add("ID2.png");
// Recognition settings
Aspose.OCR.IDCardRecognitionSettings recognitionSettings = new Aspose.OCR.IDCardRecognitionSettings();
recognitionSettings.Language = Aspose.OCR.Language.Latin;
// Recognize ID cards
List<Aspose.OCR.RecognitionResult> results = recognitionEngine.RecognizeIDCard(input, recognitionSettings);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```
