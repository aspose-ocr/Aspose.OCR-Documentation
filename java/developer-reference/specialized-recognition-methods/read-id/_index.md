---
weight: 10
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/id-card
feedback: OCRJAVA
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

To extract text from an ID card, use `RecognizeIDCard` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-id-card/).

The method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a list of recognition results containing the identity data.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "ID1.png"));
input.add(os.path.join(self.dataDir, "ID2.png"));
// Recognition settings
IDCardRecognitionSettings recognitionSettings = new IDCardRecognitionSettings();
recognitionSettings.setAllowedCharacters(CharactersAllowedType.LATIN_ALPHABET);
// Recognize ID cards
ArrayList<RecognitionResult> results = api.RecognizeIDCard(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```
