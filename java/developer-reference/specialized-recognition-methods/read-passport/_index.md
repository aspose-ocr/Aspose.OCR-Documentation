---
weight: 20
date: "2024-06-18"
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

{{% alert color="caution" %}} 
To use this recognition method, [install](/ocr/java/modules/) sparse text recognition model (**aspose-ocr-text-in-wild-v1**) in your project.
{{% /alert %}}

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

## Extracting passport details

Besides recognizing passport text, this method is capable of extracting essential information from a passport image, like date of birth, names, and more. The specific details extracted depend on the passport's origin, which is specified in the `setCountry()` method of the [passport recognition settings](/ocr/java/recognition-settings-passport/).

To retrieve the passport details, use the `GetKeywords()` method of the recognition results object. The information is returned as a [Java HashMap](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html) with key-value pairs that are specific to each country.

### Example

The following code snippet shows how to extract key details from US passport:

```java
// Initialize Aspose.OCR recognition API
AsposeOCR api = new AsposeOCR();
// Add passport image to the recognition batch
OcrInput source = new OcrInput(InputType.SingleImage);
source.add("passport.png");
// Specify the country of passport origin
PassportRecognitionSettings settings = new PassportRecognitionSettings();
settings.setCountry(Country.USA);
// Extract and parse passport details
RecognitionResult result = api.RecognizePassport(input, settings).get(0);
HashMap<String, RecognitionResult.LinesResult> keywords = result.GetKeywords();
// Output passport details
for(String key : keywords.keySet()) {
	out.print("Key: "+key);
	out.println("  Value: "+keywords.get(key).textInLine);
}
```
