---
weight: 20
date: "2024-12-18"
author: "Vladimir Lapin"
type: docs
url: /net/recognition/passport/
ai_search_scope: ocr_net
ai_search_endpoint: "https://api.aspose.cloud/v5.0/ocr/docsearch/ask"
feedback: OCRNET
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
To use this recognition method, [install](/ocr/net/modules/) sparse text recognition model (**aspose-ocr-text-in-wild-v1**) in your project.
{{% /alert %}}

Automatic passport recognition and verification is a very common task in many areas: border control, banking, security, and so on. However, manually re-typing text is an error-prone and time-consuming process, and mistakes can lead to security breaches and other undesirable consequences.

Aspose.OCR offers a special recognition algorithm that extracts text from scanned or photographed passports, which can then be automatically saved to the database or automatically verified.

To extract text from a passport image, use [`RecognizePassport`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/recognizepassport/) method of [`Aspose.OCR.AsposeOcr`](https://reference.aspose.com/ocr/net/aspose.ocr/asposeocr/) class.

This method allows you to customize recognition accuracy, performance, and other [settings](/ocr/net/recognition-settings-passport/).

The method takes [`OcrInput` object](/ocr/net/ocrinput/) and returns a [`RecognitionResult`](https://reference.aspose.com/ocr/net/aspose.ocr/recognitionresult/) object containing the passport data.

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add images to OcrInput object
Aspose.OCR.OcrInput input = new Aspose.OCR.OcrInput(Aspose.OCR.InputType.SingleImage);
input.Add("passport1.png");
input.Add("passport2.png");
// Recognize passports
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizePassport(input);
foreach(Aspose.OCR.RecognitionResult result in results)
{
	Console.WriteLine(result.RecognitionText);
}
```

## Extracting passport details

Besides recognizing passport text, this method is capable of extracting essential information from a passport image, like date of birth, names, and more. The specific details extracted depend on the passport's origin, which is specified in the `Country` parameter of the [recognition settings](/ocr/net/recognition-settings-passport/).

To retrieve the passport details, use the `GetKeywords()` method of the recognition results object. The information is returned as a [dictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2) with key-value pairs that are specific to each country.

### Example

The following code snippet shows how to extract key details from US passport:

```csharp
Aspose.OCR.AsposeOcr recognitionEngine = new Aspose.OCR.AsposeOcr();
// Add scanned passport to recognition batch
OcrInput passports = new OcrInput(InputType.SingleImage);
passports.Add("us_passport_sample.png");
// Explicitly specify that you are processing US passport
var recognitionSettings = new PassportRecognitionSettings();
recognitionSettings.Country = Aspose.OCR.Country.USA;
// Recognize passport
Aspose.OCR.OcrOutput results = recognitionEngine.RecognizePassport(passports, recognitionSettings);
// Parse passport data and output essential details along with image regions they were found in
var details = results[0].GetKeywords();
foreach (var item in details)
{
	Console.WriteLine($"{item.Key}: {item.Value.TextInLine}");
	Console.WriteLine($"Left: {item.Value.Line.X}; top: {item.Value.Line.Y}; size: {item.Value.Line.Width} x {item.Value.Line.Height}");
}
```
