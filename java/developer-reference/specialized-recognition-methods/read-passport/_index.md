---
weight: 20
date: "2023-07-14"
author: "Vladimir Lapin"
type: docs
url: /java/recognition/passport/
feedback: OCRJAVA
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

Aspose.OCR offers a special recognition algorithm that extracts text from scanned or photographed passports, which can then be automatically saved to the database or automatically verified.

To extract text from a passport image, use `RecognizePassport` method of [`AsposeOCR`](https://reference.aspose.com/ocr/java/com.aspose.ocr/AsposeOCR) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/java/recognition-settings-passport/).

The method takes [`OcrInput` object](/ocr/java/ocrinput/) and returns a list of recognition results containing the passport data.

```java
AsposeOCR api = new AsposeOCR();
// Add images to the recognition batch
OcrInput input  = new OcrInput(InputType.SingleImage);
input.add(os.path.join(self.dataDir, "passport1.png"));
input.add(os.path.join(self.dataDir, "passport2.png"));
// Recognition settings
PassportRecognitionSettings recognitionSettings = new PassportRecognitionSettings();
recognitionSettings.setLanguage(Language.Ukr);
// Recognize passports
ArrayList<RecognitionResult> results = api.RecognizePassport(input, recognitionSettings);
results.forEach((result) -> {
	System.out.println(result.recognition_text);
});
```